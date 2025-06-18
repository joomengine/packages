# JCB! Joomla Plugins

### What Are Joomla Plugins?
**Joomla Plugins** created in JCB are event-driven extensions that allow you to inject  
custom logic at key points in the Joomla application lifecycle.

These plugins are automatically built when linked to a component and compiled.  
They support both backend and CLI contexts, and are ideal for scenarios like:

- Command-line (CLI) tasks
- Scheduled cron operations
- Authentication filters
- Data transformation or validations
- System-level integrations

Each plugin can contain raw PHP, helper classes, and plugin XML configuration.  
Fields may also be used to generate configurable plugin parameters.

---
### Why Are Joomla Plugins Useful in JCB?
Joomla Plugins extend the runtime behavior of your component:

- Hook into Joomla's native event system
- Perform background logic or validations
- Execute scheduled tasks via CLI
- Access Joomla core APIs without modifying core files

Plugins are automatically compiled in the with component its linked to,  
ensuring that any custom logic tied to system events is deployed alongside your component.

They are excellent tools for modular logic injection, background automation, and clean separation of concerns.

---
### Versioning and Sharing
When you need to update Joomla Plugins in any JCB project:

- Select the plugin(s) you wish to refresh
- Click **"Reset"** to pull the latest version from this repository
- Or **Fork** this repository and point your JCB instance to your fork

This ensures your plugins are version-controlled and up-to-date,  
while still allowing full customization per project.

> Plugins are an essential part of a robust Joomla architecture — offering silent, background-driven functionality with full JCB integration.

---
### Index of Joomla Plugins


 - **Component Commands** | [Details](src/joomla_plugin/5df401b4-c9a6-42c8-b50d-87f67c8a15f3) | [Settings](src/joomla_plugin/5df401b4-c9a6-42c8-b50d-87f67c8a15f3/item.json) | Register [[[ComponentNamespace]]] Commands

@since 4.0.0
 - **Global Privacy J5** | [Details](src/joomla_plugin/8aa96d76-94e3-47d1-8dd8-f430b72ed0f7) | [Settings](src/joomla_plugin/8aa96d76-94e3-47d1-8dd8-f430b72ed0f7/item.json) | The plugin to fully integrate [[[component]]] with the privacy suite of Joomla.

### All used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")