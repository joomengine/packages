### JCB! Layout
# Recipes Modal

## Key:
```php
echo LayoutHelper::render('recipesmodal', [?]);
```

## PHP:
```php
$item = $displayData['item'] ?? null;
```

## HTML:
```html
<?php if ($item !== null): ?>
<div class="modal fade" id="recipeModal-<?php echo (int) $item->id; ?>" tabindex="-1"
		 aria-labelledby="recipeModalLabel-<?php echo (int) $item->id; ?>" aria-hidden="true">
	<div class="modal-dialog modal-lg modal-dialog-scrollable">
		<div class="modal-content border-0 shadow">
			<div class="modal-header">
				<h5 class="modal-title" id="recipeModalLabel-<?php echo (int) $item->id; ?>">
					<?php echo $item->name; ?>
				</h5>
				<button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
			</div>

			<?php if (!empty($item->image)) : ?>
				<div class="ratio ratio-16x9">
					<img src="<?php echo htmlspecialchars($item->image, ENT_QUOTES, 'UTF-8'); ?>"
							 alt="<?php echo htmlspecialchars($item->name, ENT_QUOTES, 'UTF-8'); ?>"
							 class="img-fluid w-100 h-100 object-fit-cover"
							 style="object-fit: cover;">
				</div>
			<?php endif; ?>

			<div class="modal-body">
				<p><strong><?php echo Text::_('Preparing Time'); ?>:</strong> <?php echo $item->preparing_time; ?></p>
				<p><strong><?php echo Text::_('Category'); ?>:</strong> <?php echo $item->categories_title; ?></p>
				<p><strong><?php echo Text::_('Description'); ?>:</strong> <?php echo $item->description; ?></p>
				<p><strong><?php echo Text::_('Ingredients'); ?>:</strong> soon...</p>
				<hr>
				<p class="small text-muted">
					<strong><?php echo Text::_('Created'); ?>:</strong> <?php echo $item->created; ?><br>
					<strong><?php echo Text::_('Modified'); ?>:</strong> <?php echo $item->modified; ?><br>
					<strong><?php echo Text::_('Hits'); ?>:</strong> <?php echo (int) $item->hits; ?>
				</p>
			</div>

			<div class="modal-footer">
				<button type="button" class="btn btn-secondary" data-bs-dismiss="modal"><?php echo Text::_('Close'); ?></button>
			</div>
		</div>
	</div>
</div>
<?php else: ?>
<div class="alert alert-danger" role="alert">
	<strong><?php echo Text::_('Error'); ?>:</strong> <?php echo Text::_('No recipe data was provided. Please ensure a valid item is passed to the layout.'); ?>
</div>
<?php endif; ?>
```

> Enhance your Joomla components with a reusable layout that ensures consistent design, easy updates, and full compatibility within the JCB framework.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")