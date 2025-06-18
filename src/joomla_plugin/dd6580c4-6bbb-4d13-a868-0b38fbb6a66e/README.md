### JCB! Joomla Plugin
# PreUpVer Loader (v1.0.0)
## PreUpVerLoader

This plugin is used to load PreUpVer on your website. So it adds https://cdn.jsdelivr.net/gh/Llewellynvdm/PreUpVer@1.0.0/dist/js/preupver.min.js to the header of your website. See: https://git.vdm.dev/Llewellyn/PreUpVer for more details.

### Plugin Settings
| Setting                 | Value         |
|-------------------------|---------------|
| Add Custom Class Header | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) |
| Add README              | ![yes](https://img.shields.io/badge/yes-success?style=flat-square)  |

## Class Header:
```php
use Joomla\CMS\Plugin\CMSPlugin;
use Joomla\CMS\Html\HTMLHelper;
```

## Properties & Methods:
```php
	/**
	 * Application object
	 *
	 * @var    CMSApplication
	 * @since  1.0.0
	 */
	protected  $app;

	/**
	 * This method is called before the head is compiled and allows manipulation of the head data.
	 * In this case, it's used to add a JavaScript file to the front end of the Joomla site.
	 *
	 * @return  void
	 *
	 * @since   3.0.0
	 * @throws  Exception on error.
	 */
	public function onBeforeCompileHead()
	{
		// Check if we are in the site application
		if ($this->app->isClient('site')) {
			HTMLHelper::_('script', 'https://cdn.jsdelivr.net/gh/Llewellynvdm/PreUpVer@1.0.0/dist/js/preupver.min.js', ['version' => 'auto']);
		}
	}
```

<details>
<summary>README Template</summary>

```markdown
# PreUpVer Loader ([[[plugin.version]]])

## Introduction

PreUpVer is a versatile JavaScript library designed to automatically update the version numbers of library scripts in your documentation. It identifies specific [CODE]<pre>[CODE] tags on your webpage and updates them with the latest version tag fetched from a specified repository, ensuring your documentation always displays up-to-date information.

## How It Works

PreUpVer operates by searching for [CODE]<pre>[CODE] tags with a designated class ([CODE]preupver[CODE]) and using their data attributes to perform version updates. It simplifies the process of keeping your library references up-to-date in documentation.

### Automatic Detection and Updating

When the webpage loads, PreUpVer finds all [CODE]<pre>[CODE] tags marked with the [CODE]preupver[CODE] class. It then extracts necessary details from their data attributes and updates each tag with the latest library version.

### Usage

1. **Marking [CODE]<pre>[CODE] Tags:**

   Add the [CODE]class="preupver"[CODE] to [CODE]<pre>[CODE] tags in your HTML and define the required data attributes for automatic updating:

   [CODE BLOCK]html
   <pre id="unique-id" class="preupver"
        data-api-url="https://api.github.com/repos/username/library/tags"
        data-description="Description of the library script"
        data-url="https://cdn.jsdelivr.net/gh/username/library@${version}/dist/library.min.js">
   </pre>
   [CODE BLOCK]

   Replace [CODE]unique-id[CODE], [CODE]username[CODE], [CODE]library[CODE], and other placeholders with your specific details.

2. **Attributes Explained:**

   - [CODE]id[CODE]: A unique identifier for the [CODE]<pre>[CODE] tag.
   - [CODE]data-api-url[CODE]: The API URL to fetch the latest library version.
   - [CODE]data-description[CODE]: A brief description of the library script.
   - [CODE]data-url[CODE]: The URL of the script, where [CODE]${version}[CODE] will be replaced with the latest version number.

### Example

Check out the [tests](https://git.vdm.dev/Llewellyn/PreUpVer/src/branch/master/tests/) folder for the examples we use to test if this library works as expected.

# Build Details

+ *Author*: [Llewellyn van der Merwe](mailto:joomla@vdm.io)
+ *Name*: [PreUpVer Loader](https://git.vdm.dev/Llewellyn/PreUpVer)
+ *First Build*: ###CREATIONDATE###
+ *Last Build*: ###BUILDDATE###
+ *Version*: [[[plugin.version]]]
+ *Copyright*: ###COPYRIGHT###
+ *License*: ###LICENSE###

> This **plugin** was build with a Joomla [Automated Component Builder](https://www.joomlacomponentbuilder.com).
> Developed by [Llewellyn van der Merwe](mailto:joomla@vdm.io)
```

</details>

> Extend Joomla's behaviour at key events with this customizable Plugin that integrates cleanly into your JCB-built components.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")