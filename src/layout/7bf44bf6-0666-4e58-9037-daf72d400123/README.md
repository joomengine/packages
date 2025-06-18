### JCB! Layout
# Trash Helper

## Key:
```php
echo LayoutHelper::render('trashhelper', [?]);
```

## HTML:
```html
<?php if ($displayData->state->get('filter.published') == -2 && ($displayData->canState && $displayData->canDelete)) : ?>
	<script>
		// change the class of the delete button
		jQuery("#toolbar-delete button").toggleClass("btn-danger");
		// function to empty the trash
		function emptyTrash() {
			if (document.adminForm.boxchecked.value == 0) {
				// select all the items visable
				document.adminForm.elements['checkall-toggle'].checked=1;
				Joomla.checkAll(document.adminForm.elements['checkall-toggle']);
				// check to confirm the deletion
				if(confirm('<?php echo Text::_("Are you sure you want to delete? Confirming will permanently delete the selected item(s)!") ?>')) {
					Joomla.submitbutton('<?php echo $displayData->getName(); ?>.delete');
				} else {
					document.adminForm.elements['checkall-toggle'].checked=0;
					Joomla.checkAll(document.adminForm.elements['checkall-toggle']);
				}
			} else {
				// confirm deletion of those selected
				if (confirm('<?php echo Text::_("Are you sure you want to delete? Confirming will permanently delete the selected item(s)!") ?>')) {
					Joomla.submitbutton('<?php echo $displayData->getName(); ?>.delete');
				};
			}
			return false;
		}
		// function to exit the tash state
		function exitTrash() {
			document.adminForm.filter_published.selectedIndex = 0;
			document.adminForm.submit();
			return false;
		}
	</script>
	<div class="alert alert-error">
		<?php if (empty($displayData->items)): ?>
			<h4 class="alert-heading">
				<span class="icon-trash"></span>
				<?php echo Text::_("Trash Area") ?>
			</h4>
			<p><?php echo Text::_("You are currently viewing the trash area, and you don't have any items in trash at the moment!") ?></p>
		<?php else: ?>
			<h4 class="alert-heading">
				<span class="icon-trash"></span>
				<?php echo Text::_("Trashed items") ?>
			</h4>
			<p><?php echo Text::_("You are currently viewing the trashed items.") ?></p>
			<button onclick="emptyTrash();" class="btn btn-small btn-danger">
				<span class="icon-delete" aria-hidden="true"></span>
				<?php echo Text::_("Empty trash") ?>
			</button>
		<?php endif; ?>
		<button onclick="exitTrash();" class="btn btn-small">
			<span class="icon-back" aria-hidden="true"></span>
			<?php echo Text::_("Exit trash") ?>
		</button>
	</div>
<?php endif; ?>
```

> Enhance your Joomla components with a reusable layout that ensures consistent design, easy updates, and full compatibility within the JCB framework.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")