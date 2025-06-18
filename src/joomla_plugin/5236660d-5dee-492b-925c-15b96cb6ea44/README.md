### JCB! Joomla Plugin
# Update (git.vdm.dev) J5 (v3.0.0)
## [[[component]]]

Add Access Token to easy update [[[Component]]]

### Plugin Settings
| Setting                 | Value         |
|-------------------------|---------------|
| Add Custom Class Header | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) |
| Add README              | ![no](https://img.shields.io/badge/no-blue?style=flat-square)  |

## Class Header:
```php
use Joomla\CMS\Uri\Uri;
use Joomla\CMS\Language\Text;
use Joomla\CMS\Component\ComponentHelper;
```

## Properties & Methods:
```php
	/**
	 * Affects constructor behaviour. If true, language files will be loaded automatically.
	 *
	 * @var    boolean
	 * @since  1.0.0
	 */
	protected  $autoloadLanguage = true;

	/**
	 * onInstallerBeforePackageDownload.
	 *
	 * For modification of URL and headers before package download
	 *
	 * @param   string  $url      The URL of the package being downloaded
	 * @param   array   $headers  The HTTP headers to include with the request
	 *
	 * @return  void
	 *
	 * @since   1.0
	 */
	public function onInstallerBeforePackageDownload(&$url, &$headers)
	{
		// set the URI object
		$uri = Uri::getInstance($url);
		$parts = explode('/', $uri->getPath());

		// check that this is our API
		if ($uri->getHost() == '[[[gitea_url]]]' && in_array('[[[gitea_package_name]]]', $parts))
		{
			// get the token if set
			$token = ComponentHelper::getParams('com_[[[component]]]')->get('gitea_token', false);

			// only add the Authorization header if token is set
			if ($token)
			{
				// Add the token as an Authorization header
				$headers[] = 'Authorization: token ' . $token;
			}
			else
			{
				// set the return URL
				$return = urlencode(base64_encode((string) Uri::getInstance()));
				// set the URLs
				$get_access_token_url = '"https://[[[gitea_url]]]/user/settings/applications" target="_blank" title="' . Text::_('Get Access Token') . '"';
				$set_access_token_url = '"' . Uri::root() . 'administrator/index.php?option=com_config&view=component&component=com_[[[component]]]&path=&return=' . $return . '" title="' . Text::_('Set Access Token') . '"';

				// Load the message
				$this->getApplication()->enqueueMessage(
					Text::sprintf(
						"If there was a download/update error, it's probably because the <a href=%s >API Access Token</a> for updates of [[[component]]] has not been set, you can set this access token in the <a href=%s >global options tab</a>.",
						$get_access_token_url,
						$set_access_token_url
					),
					'notice'
				);
			}
		}
	}
```

> Extend Joomla's behaviour at key events with this customizable Plugin that integrates cleanly into your JCB-built components.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")