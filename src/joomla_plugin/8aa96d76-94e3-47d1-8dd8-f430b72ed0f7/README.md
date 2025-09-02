### JCB! Joomla Plugin
# Global Privacy J5 (v2.0.0)
## [[[Component]]]

The plugin to fully integrate [[[component]]] with the privacy suite of Joomla.

### Plugin Settings
| Setting                 | Value         |
|-------------------------|---------------|
| Add Custom Class Header | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) |
| Add README              | ![yes](https://img.shields.io/badge/yes-success?style=flat-square)  |

## Class Header:
```php
use Joomla\Utilities\ArrayHelper;
use Joomla\Component\Privacy\Administrator\Plugin\PrivacyPlugin;
use Joomla\Database\DatabaseAwareTrait;
```

## Properties & Methods:
```php
	use DatabaseAwareTrait;

	/**
	 * Affects constructor behavior. If true, language files will be loaded automatically.
	 *
	 * @var    boolean
	 * @since  1.0
	 */
	protected  $autoloadLanguage = true;

	/**
	 * Performs validation to determine if the data associated with a remove information request can be processed
	 *
	 * @param   Joomla___afbb897f_f5b8_465d_9213_dae5ccf3df3d___Power  $request  The request record being processed
	 * @param   Joomla___effdaf6d_2275_425d_9f52_d4952e564d34___Power                $user     The user account associated with this request if available
	 *
	 * @return  Joomla___5c599ecf_8f58_44b4_bbaf_a47eb5d302e5___Power
	 *
	 * @since   1.0
	 */
	public function onPrivacyCanRemoveData(Joomla___afbb897f_f5b8_465d_9213_dae5ccf3df3d___Power $request, Joomla___effdaf6d_2275_425d_9f52_d4952e564d34___Power $user = null)
	{
		$status = new Joomla___5c599ecf_8f58_44b4_bbaf_a47eb5d302e5___Power();

		// This plugin only processes data for registered user accounts
		if (!$user)
		{
			return $status;
		}

		// check if the helper method is set in the component
		if (method_exists(Joomla___aebfeb9f_f8a3_42be_a21d_5db56ae30c1c___Power::class, 'onPrivacyCanRemoveData'))
		{
			Joomla___aebfeb9f_f8a3_42be_a21d_5db56ae30c1c___Power::onPrivacyCanRemoveData($this, $status, $request, $user);
		}

		return $status;
	}

	/**
	 * Processes an export request for Joomla core user data
	 *
	 * @param   Joomla___afbb897f_f5b8_465d_9213_dae5ccf3df3d___Power  $request  The request record being processed
	 * @param   Joomla___effdaf6d_2275_425d_9f52_d4952e564d34___Power                $user     The user account associated with this request if available
	 *
	 * @return  Joomla___f5e0753c_c8d9_4965_a606_9c45b37a6857___Power[]
	 *
	 * @since   1.0
	 */
	public function onPrivacyExportRequest(Joomla___afbb897f_f5b8_465d_9213_dae5ccf3df3d___Power $request, Joomla___effdaf6d_2275_425d_9f52_d4952e564d34___Power $user = null)
	{
		$domains = array();

		// This plugin only processes data for registered user accounts
		if (!$user)
		{
			return $domains;
		}

		// check if the helper method is set in the component
		if (method_exists(Joomla___aebfeb9f_f8a3_42be_a21d_5db56ae30c1c___Power::class, 'onPrivacyExportRequest'))
		{
			Joomla___aebfeb9f_f8a3_42be_a21d_5db56ae30c1c___Power::onPrivacyExportRequest($this, $domains, $request, $user);
		}

		return $domains;
	}

	/**
	 * Removes the data associated with a remove information request
	 *
	 * @param   Joomla___afbb897f_f5b8_465d_9213_dae5ccf3df3d___Power  $request  The request record being processed
	 * @param   Joomla___effdaf6d_2275_425d_9f52_d4952e564d34___Power                $user     The user account associated with this request if available
	 *
	 * @return  void
	 *
	 * @since   1.0
	 */
	public function onPrivacyRemoveData(Joomla___afbb897f_f5b8_465d_9213_dae5ccf3df3d___Power $request, Joomla___effdaf6d_2275_425d_9f52_d4952e564d34___Power $user = null)
	{
		// This plugin only processes data for registered user accounts
		if (!$user)
		{
			return;
		}

		// check if the helper method is set in the component
		if (method_exists(Joomla___aebfeb9f_f8a3_42be_a21d_5db56ae30c1c___Power::class, 'onPrivacyRemoveData'))
		{
			Joomla___aebfeb9f_f8a3_42be_a21d_5db56ae30c1c___Power::onPrivacyRemoveData($this, $request, $user);
		}
	}
```

<details>
<summary>README Template</summary>

```markdown
# ###PLUGIN_NAME### (###VERSION###)

###DESCRIPTION###

# Build Details

+ *Company*: [###COMPANYNAME###](###AUTHORWEBSITE###)
+ *Author*: [###AUTHOR###](mailto:###AUTHOREMAIL###)
+ *Version*: ###VERSION###
+ *Copyright*: ###COPYRIGHT###
+ *License*: ###LICENSE###
```

</details>

> Extend Joomla's behaviour at key events with this customizable Plugin that integrates cleanly into your JCB-built components.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")