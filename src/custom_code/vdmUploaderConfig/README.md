### JCB! Custom Code
# vdmUploaderConfig

## JCB (manual)
```
[CUSTOMCODE=vdmUploaderConfig]
```

### Code
```php
		$app = $this->app ?? Joomla___39403062_84fb_46e0_bac4_0023f766e827___Power::getApplication();

		// set the url as needed
		$url = '';
		if (method_exists($app, 'isClient') && $app->isClient('site'))
		{
			$url = Joomla___eecc143e_b5cf_4c33_ba4d_97da1df61422___Power::root();
		}

		// get the form token
		$token = Joomla___5ba38513_5c4f_4b0d_935e_49e986a6bce8___Power::getFormToken();
		$entity ??= $this->item->guid ?? 0;
		$target ??= base64_encode('[[[view]]]');

		// Define the configuration for the uploader
		$uploaderConfig = [
			"endpoint_type" => "{$url}index.php?option=com_[[[component]]]&task=ajax.[[[arg2]]]&format=json&raw=true&{$token}=1&target={$target}",
			"target_class" => "[[[arg0]]]",
			"[[[arg1]]]" => [
				"endpoint_upload" => "{$url}index.php?option=com_[[[component]]]&task=ajax.[[[arg3]]]&format=json&raw=true&{$token}=1&entity={$entity}&target={$target}",
				"endpoint_display" => "{$url}index.php?option=com_[[[component]]]&task=ajax.[[[arg4]]]&format=json&raw=true&{$token}=1&entity={$entity}&target={$target}",
				"endpoint_delete" => "{$url}index.php?option=com_[[[component]]]&task=ajax.[[[arg5]]]&format=json&raw=true&{$token}=1",
			],
		];

		// Convert the PHP array to a JavaScript object
		$uploaderConfigJson = json_encode($uploaderConfig);
		$script = "(window.VDM ??= {}).uikit ??= {}; window.VDM.uikit.config = {$uploaderConfigJson};";

		/** @var \Joomla\CMS\Document\Document $document */
		$document ??= ($this->getDocument() ?? $app->getDocument());

		// Use WebAssetManager if available (Joomla 4+), otherwise fallback
		if (method_exists($document, 'getWebAssetManager'))
		{
			/** @var \Joomla\CMS\WebAsset\WebAssetManager $wa */
			$wa = $document->getWebAssetManager();
			$wa->addInlineScript($script);
		}
		else
		{
			$document->addScriptDeclaration($script);
		}
```

> Add clean, self-contained code into your components with this reusable custom-code snippet designed for seamless integration and easy updates in JCB.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")