### JCB! Custom Code
# CascadingSelectManager JS

## JCB (manual)
```
[CUSTOMCODE=cascadingSelectManagerJS]
```

### Code
```php
/**
 * CascadingSelectManager
 *
 * Joomla 5–ready, subform-safe cascading select manager.
 * Works exclusively with <joomla-field-fancy-select> (Choices.js).
 *
 * Example chain: Country → State → City
 *
 * @version 1.8.2
 * @since   Joomla 5.x
 */
class CascadingSelectManager {
	constructor(options = {}) {
		if (!options || !Array.isArray(options.chain) || options.chain.length < 2) {
			console.error('CascadingSelectManager: The "chain" option must be an array of at least two field definitions.');
			return;
		}

		this.fieldChain = options.chain.map((configuration) => this._normalizeFieldConfiguration(configuration));
		this.matchMode = this._normalizeMatchMode(options.matchMode || 'endsWith');
		this.subformContainerClass = options.subformContainerClass || null;

		this.initialData = options.initialData || {};

		// NEW: track initialized containers safely (works for document, elements, fragments)
		this._initializedContainers = new WeakSet();

		this._initializeOnDocumentReady();
	}

	/* ----------------------------------------------------------------------
	 * Initialization
	 * ---------------------------------------------------------------------- */
	_initializeOnDocumentReady() {
		const initializeManager = () => this._initializeAllChains();

		if (document.readyState === 'loading') {
			document.addEventListener('DOMContentLoaded', initializeManager);
		} else {
			initializeManager();
		}

		// Only initialize the newly added subform row, not all rows
		document.addEventListener('subform-row-add', (event) => {
			// Joomla 5 typically provides the row on event.detail.row
			const newRow = event?.detail?.row || event?.target?.closest('.subform-repeatable-group');
			if (!newRow) return;

			if (this.subformContainerClass && !newRow.closest(`.${this.subformContainerClass}`)) {
				return;
			}

			this._initializeAllChains(newRow);
		});
	}

	_getAllContainers(rootElement = document) {
		// If a specific subform container class is configured:
		if (this.subformContainerClass) {
			// If the rootElement itself is such a container, use it directly
			if (rootElement instanceof Element && rootElement.classList.contains(this.subformContainerClass)) {
				return [rootElement];
			}
			// Otherwise, find all matching containers under rootElement
			const containers = rootElement.querySelectorAll
				? rootElement.querySelectorAll(`.${this.subformContainerClass}`)
				: [];
			if (containers.length > 0) {
				return Array.from(containers);
			}
			console.warn(`CascadingSelectManager: No subform containers found for class "${this.subformContainerClass}"`);
			return [];
		}
		// No specific class: treat the passed rootElement itself as the container
		return [rootElement];
	}

	_initializeAllChains(rootElement = document) {
		const containers = this._getAllContainers(rootElement);
		if (containers.length === 0) return;

		containers.forEach((container) => {
			// Guard: don’t re-initialize the same container twice
			if (this._initializedContainers.has(container)) return;
			this._initializedContainers.add(container);

			const firstFieldConfiguration = this.fieldChain[0];
			const firstSelectElements = this._findAllMatchingElements(container, firstFieldConfiguration.identifier, this.matchMode);

			firstSelectElements.forEach((firstSelectElement) => {
				const chainInstance = this._buildChainInstance(firstSelectElement, container);
				if (!chainInstance) return;

				// Prepare fields
				this.fieldChain.forEach((fieldConfiguration, index) => {
					const selectElement = chainInstance[fieldConfiguration.name];
					if (!selectElement) return;

					this._ensureChoicesInitialization(selectElement);

					if (index === 0 && fieldConfiguration.placeholder?.ready) {
						this._ensurePlaceholderIfEmpty(selectElement, fieldConfiguration.placeholder.ready);
					} else if (index > 0) {
						this._resetSelectElement(selectElement, fieldConfiguration.placeholder?.initial || '—');
					}
				});

				// Bind change listeners per field
				this.fieldChain.forEach((fieldConfiguration, index) => {
					const selectElement = chainInstance[fieldConfiguration.name];
					if (!selectElement) return;
					this._bindChangeListener(selectElement, async () => {
						await this._onFieldLevelChange(chainInstance, index);
					});
				});

				// Preload any existing selections
				this._preloadExistingSelections(chainInstance);
			});
		});
	}

	/* ----------------------------------------------------------------------
	 * Change Handling
	 * ---------------------------------------------------------------------- */
	async _onFieldLevelChange(chainInstance, changedFieldIndex) {
		for (let index = changedFieldIndex + 1; index < this.fieldChain.length; index++) {
			const fieldConfiguration = this.fieldChain[index];
			const selectElement = chainInstance[fieldConfiguration.name];
			if (!selectElement) continue;
			this._resetSelectElement(selectElement, fieldConfiguration.placeholder?.initial || '—');
		}

		const nextFieldIndex = changedFieldIndex + 1;
		if (nextFieldIndex >= this.fieldChain.length) return;

		const nextFieldConfiguration = this.fieldChain[nextFieldIndex];
		if (!nextFieldConfiguration.endpoint) return;

		const parentFieldConfiguration = this.fieldChain[changedFieldIndex];
		const parentSelectElement = chainInstance[parentFieldConfiguration.name];
		if (!parentSelectElement || !parentSelectElement.value) return;

		try {
			const responseData = await this._fetchDataFromServer(nextFieldConfiguration.endpoint.url, {
				[nextFieldConfiguration.endpoint.parameterKey]: parentSelectElement.value,
			});
			const nextSelectElement = chainInstance[nextFieldConfiguration.name];
			this._populateSelectElement(nextSelectElement, responseData, nextFieldConfiguration.placeholder?.ready || '—');
		} catch (error) {
			console.error(`CascadingSelectManager: Failed to fetch data for ${nextFieldConfiguration.name}`, error);
		}
	}

	/**
	 * Safely set the value for a Fancy Select (Choices.js) field
	 * and visually update it in the Joomla UI.
	 */
	async _setFancySelectValue(selectElement, valueToSelect) {
		if (!selectElement || !valueToSelect) return;

		const fancyWrapper = selectElement.closest('joomla-field-fancy-select');
		const choicesInstance =
			selectElement.choices ||
			(fancyWrapper && fancyWrapper.choicesInstance) ||
			(window.Joomla?.FieldChoices?.instances && Joomla.FieldChoices.instances[selectElement.id]) ||
			null;

		// Allow Choices to finalize rendering before setting programmatically
		await new Promise((resolve) => setTimeout(resolve, 50));

		try {
			if (choicesInstance) {
				choicesInstance.removeActiveItems();
				choicesInstance.setChoiceByValue(valueToSelect);
				selectElement.value = valueToSelect;
			} else {
				selectElement.value = valueToSelect;
			}
		} catch (err) {
			console.error(`CascadingSelectManager: Could not select value ${valueToSelect}`, err);
		}
	}

	/**
	 * Preload saved selections when the page is loaded.
	 * Supports passing initialization data (initialData)
	 * for subform rows when values are not present in DOM.
	 */
	async _preloadExistingSelections(chainInstance) {
		let subformKey = null;
		const firstSelect = chainInstance[this.fieldChain[0].name];
		if (firstSelect && firstSelect.name) {
			const match = firstSelect.name.match(/\[(\w+\d+)\]/);
			if (match) subformKey = match[1];
		}

		const preloadedValues = subformKey && this.initialData[subformKey] ? this.initialData[subformKey] : {};

		for (let index = 0; index < this.fieldChain.length - 1; index++) {
			const currentField = this.fieldChain[index];
			const nextField = this.fieldChain[index + 1];
			if (!nextField.endpoint) continue;

			const currentSelect = chainInstance[currentField.name];
			const nextSelect = chainInstance[nextField.name];
			if (!currentSelect || !nextSelect) continue;

			const currentValue =
				preloadedValues[currentField.name] ||
				currentSelect.value ||
				currentSelect.getAttribute('value');

			if (!currentValue) {
				this._resetSelectElement(nextSelect, nextField.placeholder?.initial || '—');
				break;
			}

			try {
				const data = await this._fetchDataFromServer(nextField.endpoint.url, {
					[nextField.endpoint.parameterKey]: currentValue
				});

				this._populateSelectElement(nextSelect, data, nextField.placeholder?.ready || '—');

				const nextValue =
					preloadedValues[nextField.name] ||
					nextSelect.value ||
					nextSelect.getAttribute('value') ||
					'';

				if (nextValue) {
					await this._setFancySelectValue(nextSelect, nextValue);
				}

				nextSelect.dispatchEvent(new Event('change', { bubbles: true }));
			} catch (error) {
				console.error(`CascadingSelectManager: preload failed for ${nextField.name}`, error);
				break;
			}
		}
	}

	/* ----------------------------------------------------------------------
	 * Choices.js / Fancy Select Integration
	 * ---------------------------------------------------------------------- */
	_ensureChoicesInitialization(element) {
		if (!element) return null;

		const fancyWrapper = element.closest('joomla-field-fancy-select');
		const existingChoices =
			element.choices ||
			(fancyWrapper && fancyWrapper.choicesInstance) ||
			(window.Joomla?.FieldChoices?.instances && Joomla.FieldChoices.instances[element.id]) ||
			null;

		if (existingChoices) return existingChoices;

		if (window.Joomla?.FieldChoices?.init) {
			try {
				const instance = Joomla.FieldChoices.init(element);
				return instance || null;
			} catch (e) {
				console.warn('CascadingSelectManager: Joomla FieldChoices.init failed', e);
			}
		}

		if (typeof Choices !== 'undefined') {
			try {
				const instance = new Choices(element, { shouldSort: false, searchEnabled: true });
				element.choices = instance;
				return instance;
			} catch (e) {
				console.warn('CascadingSelectManager: Choices fallback failed', e);
			}
		}

		return null;
	}

	_bindChangeListener(selectElement, handler) {
		const fancyWrapper = selectElement.closest('joomla-field-fancy-select');
		const existingChoices =
			selectElement.choices ||
			(fancyWrapper && fancyWrapper.choicesInstance) ||
			(window.Joomla?.FieldChoices?.instances && Joomla.FieldChoices.instances[selectElement.id]) ||
			null;

		if (existingChoices) {
			const container = existingChoices.containerOuter?.element || selectElement.closest('.choices');
			if (container) {
				container.addEventListener('change', handler);
				container.addEventListener('choice', () => handler());
			}
		} else {
			selectElement.addEventListener('change', handler);
		}
	}

	/* ----------------------------------------------------------------------
	 * Populate and Refresh
	 * ---------------------------------------------------------------------- */
	_populateSelectElement(element, items, placeholderText) {
		if (!element) return;

		const fancyWrapper = element.closest('joomla-field-fancy-select');
		const choicesInstance =
			element.choices ||
			(fancyWrapper && fancyWrapper.choicesInstance) ||
			(window.Joomla?.FieldChoices?.instances && Joomla.FieldChoices.instances[element.id]) ||
			null;

		const currentValue = element.value || element.getAttribute('value') || '';

		element.innerHTML = `<option value="">${this._translateText(placeholderText)}</option>`;
		if (Array.isArray(items)) {
			for (const item of items) {
				const option = document.createElement('option');
				option.value = item.value;
				option.textContent = item.text;
				if (item.value === currentValue) option.selected = true;
				element.appendChild(option);
			}
		}

		if (choicesInstance) {
			try {
				choicesInstance.clearStore();
				const formatted = items.map((i) => ({
					value: i.value,
					label: i.text,
					selected: i.value === currentValue,
					disabled: false
				}));

				choicesInstance.setChoices(
					[{ value: '', label: this._translateText(placeholderText), selected: !currentValue, disabled: true }, ...formatted],
					'value',
					'label',
					true
				);
			} catch (e) {
				console.error('CascadingSelectManager: failed to update Choices list', e);
			}
		} else {
			this._ensureChoicesInitialization(element);
		}

		element.dispatchEvent(new Event('change', { bubbles: true }));
	}

	_resetSelectElement(element, placeholderText) {
		if (!element) return;
		const choicesInstance = this._ensureChoicesInitialization(element);

		if (choicesInstance) {
			try {
				choicesInstance.clearStore();
				choicesInstance.setChoices(
					[{ value: '', label: this._translateText(placeholderText), selected: false, disabled: true }],
					'value',
					'label',
					true
				);
				return;
			} catch (e) {
				console.warn('CascadingSelectManager: Choices reset failed', e);
			}
		}

		element.innerHTML = `<option value="">${this._translateText(placeholderText)}</option>`;
		this._ensureChoicesInitialization(element);
		element.dispatchEvent(new Event('change', { bubbles: true }));
	}

	_ensurePlaceholderIfEmpty(element, placeholderText) {
		if (!element) return;
		if (!element.options || element.options.length === 0) {
			const option = document.createElement('option');
			option.value = '';
			option.textContent = this._translateText(placeholderText);
			element.appendChild(option);
		}
		this._ensureChoicesInitialization(element);
	}

	/* ----------------------------------------------------------------------
	 * Fetch
	 * ---------------------------------------------------------------------- */
	async _fetchDataFromServer(url, parameters) {
		const queryString = new URLSearchParams(parameters || {}).toString();
		try {
			const response = await fetch(`${url}${url.includes('?') ? '&' : '?'}${queryString}`, {
				headers: { 'X-Requested-With': 'XMLHttpRequest' },
			});
			if (!response.ok) throw new Error(`HTTP ${response.status}`);

			const responseData = await response.json();
			if (responseData && typeof responseData === 'object') {
				if (responseData.data !== 'undefined') {
					return  responseData.data;
				} else if (responseData.error !== 'undefined') {
					console.error(`CascadingSelectManager: Server error — ${responseData.error}`);
					return [];
				}
			}
			console.warn('CascadingSelectManager: Unexpected response format', responseData);
			return [];
		} catch (error) {
			console.error('CascadingSelectManager: Failed to fetch data', error);
			return [];
		}
	}

	/* ----------------------------------------------------------------------
	 * Utilities
	 * ---------------------------------------------------------------------- */
	_translateText(text) {
		try {
			if (window.Joomla?.Text?._) return Joomla.Text._(text);
		} catch { /* ignore */ }
		return String(text || '');
	}

	_findAllMatchingElements(rootElement, identifier, mode) {
		// guard: if rootElement can't query, fallback to document
		const scope = rootElement.querySelectorAll ? rootElement : document;
		return Array.from(scope.querySelectorAll('select[id]')).filter((element) => {
			const elementId = element.id || '';
			return (
				(mode === 'exact' && elementId === identifier) ||
				(mode === 'endsWith' && elementId.endsWith(identifier)) ||
				(mode === 'startsWith' && elementId.startsWith(identifier))
			);
		});
	}

	_buildChainInstance(firstSelectElement, rootElement) {
		const chainInstance = {};
		const firstField = this.fieldChain[0];
		chainInstance[firstField.name] = firstSelectElement;

		const firstIdentifier = firstSelectElement.id || '';
		let baseIdentifier = '';

		if (this.matchMode === 'endsWith') {
			baseIdentifier = firstIdentifier.slice(0, -String(firstField.identifier).length);
		} else if (this.matchMode === 'startsWith') {
			baseIdentifier = firstIdentifier.slice(String(firstField.identifier).length);
		}

		for (let index = 1; index < this.fieldChain.length; index++) {
			const fieldConfiguration = this.fieldChain[index];
			const selectElement = this._resolveSiblingElement(rootElement, baseIdentifier, fieldConfiguration);
			if (!selectElement) return null;
			chainInstance[fieldConfiguration.name] = selectElement;
		}
		return chainInstance;
	}

	_resolveSiblingElement(rootElement, baseIdentifier, fieldConfiguration) {
		const identifier = String(fieldConfiguration.identifier);
		let selectElement = null;

		// prefer searching within rootElement (row) first
		const scope = rootElement.querySelector ? rootElement : document;

		if (this.matchMode === 'exact') {
			selectElement = document.getElementById(identifier);
		} else if (this.matchMode === 'endsWith') {
			if (baseIdentifier) selectElement = document.getElementById(baseIdentifier + identifier);
			if (!selectElement) selectElement = this._findAllMatchingElements(scope, identifier, 'endsWith')[0];
		} else if (this.matchMode === 'startsWith') {
			if (baseIdentifier) selectElement = document.getElementById(identifier + baseIdentifier);
			if (!selectElement) selectElement = this._findAllMatchingElements(scope, identifier, 'startsWith')[0];
		}
		return selectElement;
	}

	_normalizeFieldConfiguration(configuration) {
		return {
			name: String(configuration.name || '').trim(),
			identifier: String(configuration.id || '').trim(),
			placeholder: configuration.placeholder || {},
			endpoint: configuration.endpoint
				? {
					url: String(configuration.endpoint.url || ''),
					basedOn: String(configuration.endpoint.basedOn || ''),
					parameterKey: String(configuration.endpoint.paramKey || ''),
				}
				: null,
		};
	}

	_normalizeMatchMode(mode) {
		if (mode === 1 || mode === 'exact') return 'exact';
		if (mode === 2 || mode === 'endsWith') return 'endsWith';
		if (mode === 3 || mode === 'startsWith') return 'startsWith';
		return 'endsWith';
	}
}
```

> Add clean, self-contained code into your components with this reusable custom-code snippet designed for seamless integration and easy updates in JCB.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")