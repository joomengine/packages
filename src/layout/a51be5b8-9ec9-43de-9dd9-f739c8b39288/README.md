### JCB! Layout
# Importer Columns Display

## Key:
```php
echo LayoutHelper::render('importercolumnsdisplay', [?]);
```

## PHP:
```php
$headers = null;
$file = null;

// Check if 'data' exists and is an array with at least one file
if (!empty($displayData['data']) && is_array($displayData['data']))
{
	// Retrieve the first file
	$file = array_values($displayData['data'])[0];

	// Fetch the headers for the file
	if (is_object($file) && isset($file->file_path))
	{
		$headers = Super___ff8d5fdb_2d1f_4178_bd18_a43b8efd1068___Power::_('Spreadsheet.Header')->get($file->file_path);
	}
}

// Helper function to append a field to a form element
function appendFieldToForm(\SimpleXMLElement $form, array $attributes) {
	// Create the field XML element
	$fieldXML = new \SimpleXMLElement('<field/>');
	// Set attributes for the field
	Super___1198aecf_84c6_45d2_aea8_d531aa4afdfa___Power::attributes($fieldXML, $attributes);
	// Append the field XML to the form
	Super___1198aecf_84c6_45d2_aea8_d531aa4afdfa___Power::append($form, $fieldXML);
}

// Initialize the FORM if we have headers
$map = null;
if (!empty($headers))
{
	// we update the global headers
	Joomla___aebfeb9f_f8a3_42be_a21d_5db56ae30c1c___Power::setSpreadsheetHeaders($headers);

	// get subform values
	$values = Joomla___aebfeb9f_f8a3_42be_a21d_5db56ae30c1c___Power::getItemImportSubformValues();

	// get the amount of rows expected
	$rows = count($headers);

	// Add the component field prefix
	Joomla___571422c4_0340_49f8_b846_5729c7af6ed7___Power::addFieldPrefix('[[[NamespacePrefix]]]\Component\[[[ComponentNamespace]]]\Administrator\Field');
	// Add the component rule prefix
	Joomla___571422c4_0340_49f8_b846_5729c7af6ed7___Power::addRulePrefix('[[[NamespacePrefix]]]\Component\[[[ComponentNamespace]]]\Administrator\Rule');

	// ADD any other field HERE that needs specail attention !!!

	// Load the map 'subform' field type
	$map = Joomla___571422c4_0340_49f8_b846_5729c7af6ed7___Power::loadFieldType('subform', true);

	// Create the root field element for the subform XML
	$mapXML = new \SimpleXMLElement('<field/>');
	
	// Define the attributes for the subform field
	$mapAttributes = [
		'type' => 'subform',
		'name' => 'maps',
		'label' => JustTEXT::_('Map'),
		'layout' => 'joomla.form.field.subform.repeatable-table',
		'buttons' => 'false',
		'multiple' => 'true',
		'icon' => 'list',
		'min' => $rows,
		'max' => $rows
	];

	// Set the attributes for the subform field
	Super___1198aecf_84c6_45d2_aea8_d531aa4afdfa___Power::attributes($mapXML, $mapAttributes);

	// Add the child form element inside the subform
	$childForm = $mapXML->addChild('form');
	
	// Define the attributes for the child form
	$childFormAttributes = [
		'hidden' => 'true',
		'name' => 'list_maps_modal',
		'repeat' => 'true'
	];

	// Set the attributes for the child form
	Super___1198aecf_84c6_45d2_aea8_d531aa4afdfa___Power::attributes($childForm, $childFormAttributes);

	// Build and append column field XML to the child form
	appendFieldToForm($childForm, [
		'type' => 'importcolumns',
		'name' => 'column',
		'label' => JustTEXT::_('Column'),
		'description' => JustTEXT::_('The spreadsheet columns.'),
		'class' => 'list_class',
		'readonly' => 'true',
		'layout' => 'joomla.form.field.list-fancy-select'
	]);

	// Build and append target field XML to the child form
	appendFieldToForm($childForm, [
		'type' => 'targetfields',
		'name' => 'target',
		'label' => JustTEXT::_('System Target Fields'),
		'description' => JustTEXT::_('The system target database fields.'),
		'message' => JustTEXT::_('Input Required'),
		'class' => 'list_class',
		'layout' => 'joomla.form.field.list-fancy-select'
	]);

	// Setup the subform with the constructed XML
	$map->setup($mapXML, $values, 'vdm_import');
}
```

## HTML:
```html
<?php echo LayoutHelper::render('filedisplay', $displayData); ?>
<?php if ($map === null): ?>
	<?php echo Text::_('Spreadsheet seems to have no headers set! There was an error!'); ?>
<?php else: ?>
	<div id="subform-display-area">

		<?php echo $map->input; ?>

		<input type="hidden" name="vdm_import[file]" value="<?php echo $file->guid; ?>">

		<joomla-toolbar-button id="toolbar-download-custom-button-saveimportmap" task="importer.saveImportMap">
			<div class="d-grid">
				<button class="button-download custom-button-saveimportmap btn btn-primary" type="button">
					<span class="icon-download custom-button-saveimportmap" aria-hidden="true"></span>
					<?php echo Text::_('Import'); ?>
				</button>
			</div>
		</joomla-toolbar-button>
	</div>
<?php endif;  ?>
```

> Enhance your Joomla components with a reusable layout that ensures consistent design, easy updates, and full compatibility within the JCB framework.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")