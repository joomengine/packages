# JCB! Joomla Components

### What Are Joomla Components in JCB?
In Joomla Component Builder (JCB), a Joomla Component is the top-level unit that brings everything together.

It acts as the central container — compiling all attached entities and logic into a complete, versioned, installable Joomla extension.

A Component includes:

- Admin Views (core data tables with fields and ACLs)
- Site Views (frontend output)
- Custom Admin Views (customized backend interfaces)
- Modules & Plugins (packaged alongside)
- Custom Code (injectable and reusable)
- Files and Folders (media, scripts, assets)
- MySQL Tweaks & Schema Updates
- PHP Helper Classes
- Component Configurations (global parameters)
- Placeholders & Overrides
- Dynamic Dashboards (overview screens)
- Routing Setup (site and admin)
- Version Definitions (Joomla 3, 4, 5 support)
- README, Wikis & Docs (optional, for internal reference)

Every entity you build in JCB is ultimately assembled into one or more Joomla Components — which are then compiled into installable packages, ready for use or distribution.

---
### What Makes Components So Central?
Components control the following:

- Which views, modules, plugins, and helpers are packaged
- How the database is initialized or migrated (via tweaks)
- Where assets are placed in the Joomla filesystem
- Which version of Joomla the output is compatible with
- How the component is installed, updated, and distributed
- What language files, readmes, and wikis are bundled
- Who authored the component and where it lives in Git

> Components are the single point of truth for defining your extension. Once everything else is configured — fields, views, snippets, layouts — you bind them all together through the Component.

---
### Version Control, Syncing & Collaboration
JCB Components support:

- Branch-specific configuration (Joomla 3, 4, 5)
- Component-level versioning and changelogs
- Resetting from a central repository
- Forking to maintain your own variants
- Pushing updates upstream or into shared team forks

They can also be extended via init/reset/update workflows, just like all other JCB entities.

This makes them ideal for distributed teams, client-specific forks, and open-source extension development.

> A Component in JCB isn't just a bundle of files — it's a fully-defined application package that carries the design, data, logic, and behaviour of your Joomla extension.

---
### Index of Joomla Components


 - **Demo J4** | [Details](src/joomla_component/d7d3bc04-6272-470a-91d1-e091ecb10ab6) | [Settings](src/joomla_component/d7d3bc04-6272-470a-91d1-e091ecb10ab6/item.json) | Demo Component
 - **Demo J5** | [Details](src/joomla_component/efde995e-60aa-4b39-b644-44349dfb660d) | [Settings](src/joomla_component/efde995e-60aa-4b39-b644-44349dfb660d/item.json) | Demo Component
 - **HelloWorld (public)** | [Details](src/joomla_component/3745af8f-f96b-4e17-831e-eb4062cd4389) | [Settings](src/joomla_component/3745af8f-f96b-4e17-831e-eb4062cd4389/item.json) | Hello World
 - **eHealth Portal** | [Details](src/joomla_component/eaabada6-9a90-4dc8-a3ca-22d275f4ec64) | [Settings](src/joomla_component/eaabada6-9a90-4dc8-a3ca-22d275f4ec64/item.json) | Portal for mobile health clinics

### All used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")