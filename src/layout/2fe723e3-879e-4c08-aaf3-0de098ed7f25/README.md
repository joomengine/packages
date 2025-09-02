### JCB! Layout
# Table

## Key:
```php
echo LayoutHelper::render('table', [?]);
```

## PHP:
```php
// Extract all keys from $displayData as individual variables.
extract($displayData);

// Assign default values for variables that might not be present in $displayData.

// The 'table_id' parameter, defaulting to a randomly generated value if not set or is null.
$table_id = $id ?? Super___1f28cb53_60d9_4db1_b517_3c7dc6b429ef___Power::random(7);

// The 'name' parameter, defaulting to false if not set or is null.
$name ??= false;

// The 'table_class' parameter, defaulting to 'uk-table' if not set or is null.
$table_class ??= 'uk-table';

// The 'table_other_class' parameter, defaulting to '' if not set or is null.
$table_other_class = !empty($table_other_class ?? '') ? ' ' . $table_other_class : '';

// The 'table_container_class' parameter, defaulting to 'uk-overflow-auto' if not set or is null.
$table_container_class ??= 'uk-overflow-auto';

// The 'headers' parameter, defaulting to an array of default header values if not set or is null.
$headers ??= [Text::_('No'), Text::_('Headers'), Text::_('Found')];

// The 'items' parameter, defaulting to 6 if not set or is null.
$items ??= 6;

// The 'default_items_number' parameter, defaulting to 0 if not set or is null.
$default_items_number ??= 0;

// tweak to add empty rows
$items_number = 0;
if (is_array($items))
{
	$items_number = count((array) $items);
}
elseif (is_numeric($items))
{
	$items_number = (int) $items;
}
$add_items = 0;
if ($default_items_number > $items_number)
{
	$add_items = round($default_items_number - $items_number);
}
```

## HTML:
```html
<div class="<?php echo $table_container_class; ?>">
	<table id="<?php echo $table_id; ?>" class="<?php echo $table_class; ?><?php echo $table_other_class; ?>">
		<thead>
			<?php if (is_array($headers)): ?>
				<?php if ($name): ?>
				<tr>
					<th colspan="<?php echo count($headers); ?>" style="text-align:center"><b><?php echo $name; ?></b></th>
				</tr>
				<?php endif; ?>
				<tr>
				<?php foreach($headers as $code_name => $header): ?>
					<?php 
						if (is_numeric($code_name))
						{
							$code_name = Super___1f28cb53_60d9_4db1_b517_3c7dc6b429ef___Power::safe($header);
						}
 					?>
					<th data-name="<?php echo $code_name; ?>"><?php echo $header; ?></th>
				<?php endforeach; ?>
				</tr>
			<?php elseif (is_numeric($headers)): ?>
				<?php if ($name): ?>
				<tr>
					<th colspan="<?php echo (int) $headers; ?>" style="text-align:center"><b><?php echo $name; ?></b></th>
				</tr>
				<?php endif; ?>
				<tr style="position: absolute; top: -9999px; left: -9999px;">
				<?php for( $row = 0; $row < $headers; $row++): ?>
					<th><?php echo Super___1f28cb53_60d9_4db1_b517_3c7dc6b429ef___Power::safe($row); ?></th>
				<?php endfor; ?>
				</tr>
			<?php endif; ?>
		</thead>
		<tbody>
			<?php echo Joomla___7ab82272_0b3d_4bb1_af35_e63a096cfe0b___Power::render('rows', ['headers' => $headers, 'items' => $items]); ?>
			<?php if ($add_items > 0): ?>
				<?php echo Joomla___7ab82272_0b3d_4bb1_af35_e63a096cfe0b___Power::render('rows', ['headers' => $headers, 'items' => $add_items]); ?>
			<?php endif; ?>
		</tbody>
	</table>
</div>
<?php
// Initialize the table if [init is not set], or [is true]
// To stop initialization set $displayData['init'] = false;
if (!isset($displayData['init']) || $displayData['init']) :
?>
<script type="text/javascript">
document.addEventListener('DOMContentLoaded', function() {
	var <?php echo $table_id; ?> = new DataTable('#<?php echo $table_id; ?>', {
		paging: false,
		select: true
	});
});
</script>
<?php endif; ?>
```

> Enhance your Joomla components with a reusable layout that ensures consistent design, easy updates, and full compatibility within the JCB framework.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")