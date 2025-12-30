### JCB! Layout
# File Display Engine

## Key:
```php
echo LayoutHelper::render('demolookfiledisplay', [?]);
```

## PHP:
```php
// Initialize
$data   = $displayData['data'] ?? [];
$removeDelete = $displayData['remove_delete'] ?? false;

// Group images by base key (icon__, thumb__, main__)
$bucket = [];
$files =  [];
foreach ($data as $file)
{
	$key  = str_replace(['icon__', 'thumb__', 'main__'], '', $file->name);
	$type = str_starts_with($file->name, 'icon__')
		? 'icon'
		: (str_starts_with($file->name, 'thumb__')
			? 'thumb'
			: (str_starts_with($file->name, 'main__') ? 'main' : null));

	if ($type !== null) { $bucket[$key][$type] = $file; } else { $files[] = $file; }
}

// Extract grouped images for display
$images = !empty($bucket) ? array_values($bucket) : [];
```

## HTML:
```html
<?php if (!empty($data)) : ?>
<?php if (!empty($files)) : ?>
<ul class="uk-list uk-list-divider">
<?php foreach ($files as $file) : ?>
	<li>
	<?php if ($removeDelete) : ?>
	<a class="uk-button uk-button-default uk-width-1-1" href="<?php echo $file->link; ?>" download>
		(<?php echo $file->type_name; ?>)
		<?php echo $file->name; ?>
	</a>
	<?php else : ?>
	<div id="<?php echo $file->guid; ?>"
		 class="uk-button-group uk-width-1-1 uk-margin-small-bottom">
		<a class="uk-button uk-button-default uk-width-3-4"
		   href="<?php echo $file->link; ?>" download>
			(<?php echo $file->type_name; ?>)
			<?php echo $file->name; ?>
		</a>
		<button type="button"
				class="uk-button uk-button-danger uk-width-1-4"
				uk-icon="trash"
				onclick="VDMDeleteFile('file_vdm_uploader', '<?php echo $file->guid; ?>');">
		</button>
	</div>
	<?php endif; ?>
	</li>
<?php endforeach; ?>
</ul>
<?php endif; ?>
<?php if (!empty($images)) : ?>
<div class="uk-margin">
	<div class="uk-slider-container-offset" uk-slider>
		<div class="uk-position-relative uk-visible-toggle">
			<div class="uk-slider-items uk-child-width-1-4@s" uk-grid uk-lightbox="animation: slide">
			<?php foreach ($images as $fileSet) : ?>
			<?php
				$name       = $fileSet['main']->name ?? 'unknown';
				$mainGuid   = $fileSet['main']->guid ?? null;
				$thumbGuid  = $fileSet['thumb']->guid ?? null;
				$iconGuid   = $fileSet['icon']->guid ?? null;
				$mainLink   = $fileSet['main']->link ?? null;
				$thumbLink  = $fileSet['thumb']->link ?? null;
				$iconLink   = $fileSet['icon']->link ?? null;
				$mediaLink  = $mainLink ?? $thumbLink ?? $iconLink;
				$deleteList = array_filter([$mainGuid, $thumbGuid, $iconGuid]);
				$buttonSize = count($deleteList);
			?>
			<div id="<?php echo $mainGuid ?? uniqid('img_'); ?>">
				<div class="uk-card uk-card-body uk-box-shadow-small uk-box-shadow-hover-large">
					<div class="uk-card-media-top">
						<a class="uk-inline"
						   href="<?php echo $mainLink ?? $mediaLink; ?>"
						   data-caption="<?php echo $name; ?>">
							<img src="<?php echo $mediaLink; ?>"
								 width="600"
								 height="600"
								 alt="<?php echo $name; ?>">
						</a>
					</div>

					<div class="uk-card-body uk-padding-remove">
						<div class="uk-margin">
							<div class="uk-button-group uk-width-1-1">
							<?php if ($mainLink) : ?>
								<a class="uk-button uk-button-primary uk-button-small uk-width-1-<?php echo $buttonSize; ?>"
								   href="<?php echo $mainLink; ?>" download>
									<?php echo Text::_('Large'); ?>
								</a>
							<?php endif; ?>

							<?php if ($thumbLink) : ?>
								<a class="uk-button uk-button-primary uk-button-small uk-width-1-<?php echo $buttonSize; ?>"
								   href="<?php echo $thumbLink; ?>" download>
									<?php echo Text::_('Thumb'); ?>
								</a>
							<?php endif; ?>

							<?php if ($iconLink) : ?>
								<a class="uk-button uk-button-primary uk-button-small uk-width-1-<?php echo $buttonSize; ?>"
								   href="<?php echo $iconLink; ?>" download>
									<?php echo Text::_('Icon'); ?>
								</a>
							<?php endif; ?>
							</div>
						</div>
					</div>

					<div class="uk-card-footer">
						<button class="uk-button uk-button-danger uk-width-1-1"
							type="button" uk-icon="trash"
							onclick="VDMDeleteFiles('file_vdm_uploader', <?php echo $this->escape(json_encode($deleteList)); ?>);">
						</button>
					</div>
				</div>
			</div>
			<?php endforeach; ?>
			</div>
		</div>
		<ul class="uk-slider-nav uk-dotnav uk-flex-center uk-margin"></ul>
	</div>
</div>
<?php endif; ?>
<?php endif; ?>
```

> Enhance your Joomla components with a reusable layout that ensures consistent design, easy updates, and full compatibility within the JCB framework.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")