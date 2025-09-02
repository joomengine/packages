### JCB! Layout
# Modal

## Key:
```php
echo LayoutHelper::render('modal', [?]);
```

## PHP:
```php
// Extract all keys from $displayData as individual variables.
extract($displayData);

// Assign default values for variables that might not be present in $displayData.

// The 'id' parameter, defaulting to a random string if not set.
$id ??= Super___1f28cb53_60d9_4db1_b517_3c7dc6b429ef___Power::random(7);

// The 'full' parameter, defaulting to false if not set or is null.
$full = (isset($full) && $full) ? true : false;

// The 'header' parameter, defaulting to false if not set or is null.
$header ??= false;

// The 'header_class' parameter, defaulting to 'uk-modal-title' if not set or is null.
$header_class ??= 'uk-modal-title';

// The 'header_class_other' parameter, if set, appends additional class to 'header_class', otherwise retains original 'header_class'.
$header_class = isset($header_class_other) ? $header_class . ' ' . $header_class_other : $header_class;

// The 'body_class' parameter, added if set, otherwise defaults to 'uk-modal-body'.
$body_class = isset($body_class) ? ' class="' . $body_class . '"' : ' class="uk-modal-body"';

// The 'content' parameter, defaulting to an empty string if not set.
$content ??= '';

// The 'buttons' parameter, defaulting to null if not set.
$buttons ??= null;

// The 'buttons_class' parameter, defaulting to an empty string if not set.
$buttons_class ??= '';

// The 'buttons_id' parameter, defaulting to an empty string if not set.
$buttons_id ??= '';

// The 'close' parameter, set to false if explicitly set to false, otherwise defaults to true.
$close = isset($close) && !$close ? false : true;

// The 'overflow' parameter, defaulting to 'uk-overflow-auto' unless set to false.
$overflow = isset($overflow) && !$overflow ? '' : ' uk-overflow-auto';

// The 'dialog_class' parameter, defaulting to 'uk-modal-dialog' if not set or empty.
$dialog_class ??= 'uk-modal-dialog';

// Set the full modal behavior when 'full' is true.
if ($full)
{
	// The 'modal_class' parameter, defaulting to an empty string if not set.
	$modal_class = $modal_class ?? '';

	// The 'modal_class' is wrapped with full modal classes if 'full' is true.
	$modal_class = ' class="uk-modal-full ' . $modal_class . '"';

	// Change 'class_close' to the full modal close button style when 'full' is true.
	$class_close = ' class="uk-modal-close-full uk-close-large"';
}
else
{
	// The 'modal_class' parameter, defaulting to an empty string unless provided.
	$modal_class = isset($modal_class) ? ' class="' . $modal_class . '"' : '';

	// The default close button class.
	$class_close = ' class="uk-modal-close-default"';
}
```

## HTML:
```html
<div id="<?php echo $id; ?>"<?php echo $modal_class; ?> uk-modal>
	<div class="<?php echo $dialog_class; ?>">

		<?php if ($close): ?><button<?php echo $class_close; ?> type="button" uk-close></button><?php endif; ?>

		<?php if ($header): ?>
			<?php if (strpos($header, 'uk-navbar') !== false || strpos($header, 'uk-modal-header') !== false): ?>
				<?php echo $header; ?>
			<?php else: ?>
				<div class="uk-modal-header">
					<h2 class="<?php echo $header_class; ?>"><?php echo $header; ?></h2>
				</div>
			<?php endif; ?>
		<?php endif; ?>

		<div<?php echo $body_class; ?><?php echo $overflow; ?>>
			<?php echo $content; ?>
		</div>

		<?php if ($buttons !== null): ?>
		<div class="uk-modal-footer uk-text-right">
			<?php if (!empty($buttons_class) || !empty($buttons_id)): ?>
				<div class="<?php echo $buttons_class; ?>" id="<?php echo $buttons_id; ?>">
			<?php endif; ?>
			<?php foreach ($buttons as $button): ?>
				<?php
					$id_ = $button['id'] ?? Super___1f28cb53_60d9_4db1_b517_3c7dc6b429ef___Power::random(7);
					$class =  $button['class'] ?? 'uk-button uk-button-default';
					$class .= (isset($button['close']) && $button['close']) ? ' uk-modal-close' : '';
					$name = (isset($button['name'])) ? $button['name'] : ((isset($button['close']) && $button['close']) ? Text::_('Cancel') : Text::_('Save'));
					$onclick = (isset($button['onclick'])) ? ' onclick="' . $button['onclick'] . '"' : '';
					$disabled = !empty($button['readonly']) || !empty($button['disabled']) ? ' disabled="disabled"' : '';
				?>
				<button id="<?php echo $id_; ?>" class="<?php echo $class; ?>" type="button"<?php echo $onclick . $disabled; ?>><?php echo $name; ?></button>
			<?php endforeach; ?>
			<?php if (!empty($buttons_class) || !empty($buttons_id)): ?>
				</div>
			<?php endif; ?>
		</div>
		<?php endif; ?>
	</div>
</div>
```

> Enhance your Joomla components with a reusable layout that ensures consistent design, easy updates, and full compatibility within the JCB framework.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")