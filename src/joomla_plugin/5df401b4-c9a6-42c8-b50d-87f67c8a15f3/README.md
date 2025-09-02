### JCB! Joomla Plugin
# Component Commands (v1.0.0)
## [[[ComponentNamespace]]]Commands

Register [[[ComponentNamespace]]] Commands

@since 4.0.0

### Plugin Settings
| Setting                 | Value         |
|-------------------------|---------------|
| Add Custom Class Header | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) |
| Add README              | ![no](https://img.shields.io/badge/no-blue?style=flat-square)  |

## Class Header:
```php
###POWER_AUTOLOADER###

use Joomla\Application\ApplicationEvents;
use Joomla\CMS\Plugin\CMSPlugin;
use Joomla\Event\SubscriberInterface;
use Joomla\CMS\Factory;
use Joomla\CMS\Console\Loader\WritableLoaderInterface;
```

## Properties & Methods:
```php
	/**
	 * Returns an array of events this plugin is subscribing to.
	 *
	 * @return array
	 * @since 4.0.0
	 */
	public static function getSubscribedEvents(): array
	{
		// Return an array of event names and corresponding callback methods
		return [
			ApplicationEvents::BEFORE_EXECUTE => 'onBeforeExecute',
		];
	}

	/**
	 * Registers the CLI command.
	 *
	 * @return void
	 * @since 4.0.0
	 */
	public function onBeforeExecute(): void
	{
		// Register the command in the DI container
		$serviceId = '[[[component]]].importcommand';

		Factory::getContainer()->share(
			$serviceId,
			function (\Psr\Container\ContainerInterface $container) {
				return new Super___647316a5_eb42_4bec_82dd_ca0dc2861ad3___Power();
			},
			true
		);

		// Add the command to the Joomla CLI loader
		Factory::getContainer()
			->get(WritableLoaderInterface::class)
			->add('[[[component]]]:Item:import', $serviceId);
	}
```

> Extend Joomla's behaviour at key events with this customizable Plugin that integrates cleanly into your JCB-built components.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")