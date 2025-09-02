### JCB! Layout
# File Display Engine

## Key:
```php
echo LayoutHelper::render('demolookfiledisplay', [?]);
```

## PHP:
```php
$images = [];
```

## HTML:
```html
<?php if (!empty($displayData) && !empty($displayData['data'])): ?>
	<ul class="uk-list uk-list-divider">
		<?php foreach ($displayData['data'] as $file): ?>
		<?php if ($file->task == 'image'): ?>
		<?php $images[] =  $file; ?>
		<?php else: ?>
		<li>
		<?php if (isset($displayData['remove_delete'])) : ?>
			<a class="uk-button uk-button-default uk-width-1-1" href="<?php echo $file->link; ?>" download>(<?php echo $file->type_name; ?>) <?php echo $file->name; ?></a>
		<?php else: ?>
			<div id="<?php echo $file->guid; ?>" class="uk-button-group uk-width-1-1 uk-margin-small-bottom">
				<a class="uk-button uk-button-default uk-width-3-4" href="<?php echo $file->link; ?>" download>(<?php echo $file->type_name; ?>) <?php echo $file->name; ?></a>
				<button type="button" class="uk-button uk-button-danger uk-width-1-4" uk-icon="trash" onclick="VDMDeleteFile('file_vdm_uploader', '<?php echo $file->guid; ?>');"></button>
			</div>
		<?php endif; ?>
		</li>
		<?php endif; ?>
		<?php endforeach; ?>
	</ul>
	<?php if ($images !== []): ?>
		<ul class="uk-list uk-list-divider">
			<?php foreach ($images as $file): ?>
			<li>
			<div class="uk-height-medium uk-flex uk-flex-center uk-flex-middle uk-background-cover uk-light" data-src="<?php echo $file->link; ?>" uk-img>
			<h1><?php echo $file->type_name; ?></h1>
			</div>
			<?php if (isset($displayData['remove_delete'])) : ?>
				<a class="uk-button uk-button-default uk-width-1-1" href="<?php echo $file->link; ?>" download>(<?php echo $file->type_name; ?>) <?php echo $file->name; ?></a>
			<?php else: ?>
				<div id="<?php echo $file->guid; ?>" class="uk-button-group uk-width-1-1 uk-margin-small-bottom">
					<a class="uk-button uk-button-default uk-width-3-4" href="<?php echo $file->link; ?>" download>(<?php echo $file->type_name; ?>) <?php echo $file->name; ?></a>
					<button type="button" class="uk-button uk-button-danger uk-width-1-4" uk-icon="trash" onclick="VDMDeleteFile('file_vdm_uploader', '<?php echo $file->guid; ?>');"></button>
				</div>
			<?php endif; ?>
			</li>
			<?php endforeach; ?>
		</ul>
	<?php endif; ?>
<?php endif; ?>
```

> Enhance your Joomla components with a reusable layout that ensures consistent design, easy updates, and full compatibility within the JCB framework.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")