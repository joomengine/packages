# JCB! Layouts

### What Are JCB Layouts?
JCB Layouts are **modular Joomla layout files** managed via the [JCB](https://www.joomlacomponentbuilder.com) GUI.  
They are equivalent to Joomla's native layout override files (`/layouts`) and follow the same design principles.

With JCB Layouts, you can define reusable, customizable HTML+PHP views:

- Rendered from anywhere in your component (admin or site)
- Encapsulated in clean, template-driven blocks
- Fully namespace-aware and overridable like native Joomla layouts

This allows your components to remain **cleaner, more maintainable, and DRY** (Don't Repeat Yourself).

---
### Why Use Layouts in JCB?
JCB Layouts help you:

- Extract reusable markup from views, fields, and modules
- Maintain structural consistency across your component
- Simplify changes by editing one file instead of many
- Allow for override support via Joomla templates

They're ideal for:
- Form row rendering
- Repeated output (like items in a loop)
- Conditionals and dynamic display logic

---
### How Do You Manage Layouts in JCB?
All Layouts are version-controlled and managed inside JCB's GUI under the **Layouts** tab.

To use a layout from a repository:

1. Click the **Init** button inside the Layouts area.
2. Choose a repository to load Layouts from.
3. Select the specific Layout(s) you want to import.
4. The Layout will now be available in your JCB project.

You can:

- **Reset** a Layout to sync with its upstream version
- **Push** your custom Layouts if you have write access
- Or **Fork** this repository to manage your own Layout collection

> This lets you integrate upstream improvements while maintaining your own customization workflow.

---
### Index of JCB Layouts


 - **File Display Engine** | [Details](src/layout/6e4e5acc-8a7c-49ca-be53-8f8d95bd4163) | [Settings](src/layout/6e4e5acc-8a7c-49ca-be53-8f8d95bd4163/item.json) | File Display Engine
 - **Importer Columns Display** | [Details](src/layout/a51be5b8-9ec9-43de-9dd9-f739c8b39288) | [Settings](src/layout/a51be5b8-9ec9-43de-9dd9-f739c8b39288/item.json) | Importer Columns Display
 - **Importer Easy Mapping** | [Details](src/layout/c4d0c28e-eb98-4c0d-a91e-34096e5606fe) | [Settings](src/layout/c4d0c28e-eb98-4c0d-a91e-34096e5606fe/item.json) | Importer Easy Mapping
 - **Importer Messages Log** | [Details](src/layout/0777dd83-d0dd-4fb1-8a31-13013dfc5dde) | [Settings](src/layout/0777dd83-d0dd-4fb1-8a31-13013dfc5dde/item.json) | Importer Messages Log
 - **Input** | [Details](src/layout/3c3f6271-d660-4b79-9ab2-3bf2090eded1) | [Settings](src/layout/3c3f6271-d660-4b79-9ab2-3bf2090eded1/item.json) | Input
 - **Input Box** | [Details](src/layout/eeea4dfb-6c1a-4e42-9eb7-faf98e0eb89b) | [Settings](src/layout/eeea4dfb-6c1a-4e42-9eb7-faf98e0eb89b/item.json) | Input Box
 - **Joomla! Mastodon Feed** | [Details](src/layout/9dc804de-f98b-4db9-9b83-4034184c3992) | [Settings](src/layout/9dc804de-f98b-4db9-9b83-4034184c3992/item.json) | Joomla! Mastodon Feed
 - **Modal** | [Details](src/layout/0eb94218-5798-4170-9ce5-5cf11607086d) | [Settings](src/layout/0eb94218-5798-4170-9ce5-5cf11607086d/item.json) | Modal
 - **Radio** | [Details](src/layout/7f6ff7df-4444-40ad-a7bf-5d126d6feac7) | [Settings](src/layout/7f6ff7df-4444-40ad-a7bf-5d126d6feac7/item.json) | Radio
 - **Radio Box** | [Details](src/layout/0075f54e-d953-4379-8476-918bb6684d0b) | [Settings](src/layout/0075f54e-d953-4379-8476-918bb6684d0b/item.json) | Radio Box
 - **Recipes Card Body** | [Details](src/layout/d9797f3d-6d22-47a7-bba6-45be5bd3a4e3) | [Settings](src/layout/d9797f3d-6d22-47a7-bba6-45be5bd3a4e3/item.json) | Recipes Card Body
 - **Recipes Modal** | [Details](src/layout/dbcc89a3-75eb-48f3-8982-69c0fa2b0a01) | [Settings](src/layout/dbcc89a3-75eb-48f3-8982-69c0fa2b0a01/item.json) | Recipes Modal
 - **Rows** | [Details](src/layout/72965abd-370c-4a16-a536-72cfd001e5dd) | [Settings](src/layout/72965abd-370c-4a16-a536-72cfd001e5dd/item.json) | Rows
 - **Select** | [Details](src/layout/0fca5d9a-a239-4caf-b5df-42667c972dc0) | [Settings](src/layout/0fca5d9a-a239-4caf-b5df-42667c972dc0/item.json) | Select
 - **Select Box** | [Details](src/layout/bb4c6361-c967-4b41-86e0-10d41e3ecf07) | [Settings](src/layout/bb4c6361-c967-4b41-86e0-10d41e3ecf07/item.json) | Select Box
 - **Table** | [Details](src/layout/2fe723e3-879e-4c08-aaf3-0de098ed7f25) | [Settings](src/layout/2fe723e3-879e-4c08-aaf3-0de098ed7f25/item.json) | Table
 - **Textarea** | [Details](src/layout/248e0459-ecb6-4197-9cda-824ec8285461) | [Settings](src/layout/248e0459-ecb6-4197-9cda-824ec8285461/item.json) | Textarea
 - **Textarea Box** | [Details](src/layout/7b52a2a8-63a0-42db-9c58-108b21f2ae63) | [Settings](src/layout/7b52a2a8-63a0-42db-9c58-108b21f2ae63/item.json) | Textarea Box
 - **Trash Helper** | [Details](src/layout/7bf44bf6-0666-4e58-9037-daf72d400123) | [Settings](src/layout/7bf44bf6-0666-4e58-9037-daf72d400123/item.json) | Trash Helper Layout

### All used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")