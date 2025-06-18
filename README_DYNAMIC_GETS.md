# JCB! Dynamic Gets

### What Are Dynamic Gets?
Dynamic Gets in JCB are **graphically designed database queries** that define how data should be fetched,  
joined, filtered, and structured using a **easy selection query builder** interface.

They act as a visual abstraction over SQL joins and filters, comparable to:

- **Visual Query Builders**
- **ORM Relationship Graphs**
- **Custom Query Composition Engines**

Dynamic Gets allow you to:
- Choose a **primary table**
- Join **multiple related tables**
- Select fields from across those joins
- Apply **filters**, **WHERE clauses**, **ordering**, and **grouping** — all from within a GUI.

JCB then auto-generates:
- The complete **SQL JOIN** logic
- Any **Joomla-compliant API interaction**
- The **PHP model code** required to support the query

---
### How Do Dynamic Gets Integrate Into Views?
Each **Site View** or **Custom Admin View** requires a **main Dynamic Get**,  
which defines how its item or list data is fetched from the database.

But that's not all: you can attach multiple additional Dynamic Gets to a single view,  
enabling you to **merge data from completely different tables** — dynamically, cleanly, and consistently.

JCB intelligently ensures that the resulting component:
- Uses secure and efficient Joomla API calls
- Avoids repetitive logic
- Embeds the Dynamic Get logic **directly into the component's models**

This eliminates the need for hand-crafted query code, while maintaining full control and extensibility.

---
### Reset, Fork, or Customize
Just like other JCB entities, Dynamic Gets support a Git-based update workflow:

- **Init**: Pull from a remote repository
- **Reset**: Sync with upstream versions
- **Push**: Submit updates (if you have write access)
- **Fork**: Maintain your own version of dynamic queries

This lets you customize, evolve, and share query logic without rewriting or copy-pasting.

Whether you're building for:
- Deep reporting
- Cross-table analytics
- Complex filter-based list views

> Dynamic Gets combine power, flexibility, and GUI-driven convenience — helping you build smarter, faster, and more maintainable Joomla components.

---
### Index of Dynamic Gets


 - **Greeting** | [Details](src/dynamic_get/66fd1d43-860c-45c9-821a-b3364e864f64) | [Settings](src/dynamic_get/66fd1d43-860c-45c9-821a-b3364e864f64/item.json)
 - **GreetingList** | [Details](src/dynamic_get/08516416-4d1d-4850-83ae-27e289b8a006) | [Settings](src/dynamic_get/08516416-4d1d-4850-83ae-27e289b8a006/item.json)
 - **Item Importer** | [Details](src/dynamic_get/ebfab0ae-d368-4d2a-807b-c9d2d0809a60) | [Settings](src/dynamic_get/ebfab0ae-d368-4d2a-807b-c9d2d0809a60/item.json)
 - **Looking** | [Details](src/dynamic_get/98e6ea56-0911-4d89-b1f4-8f0bb1e4aa5a) | [Settings](src/dynamic_get/98e6ea56-0911-4d89-b1f4-8f0bb1e4aa5a/item.json)
 - **Looks** | [Details](src/dynamic_get/32b3ae7d-8aa8-47f1-ab2e-30076ddaa029) | [Settings](src/dynamic_get/32b3ae7d-8aa8-47f1-ab2e-30076ddaa029/item.json)

### All used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")