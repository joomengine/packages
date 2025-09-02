# JCB! Admin Views

### What Are Admin Views?
**Admin Views** form the foundational interface layer of every JCB-built Joomla component.

Each Admin View is tightly bound to a database table and automatically generates all required:
- **Forms**
- **Models**
- **Controllers**
- **List and Edit Views**
- **Permission handling** (ACL)
- **Field validation and access control**

Admin Views are mandatory. Every JCB component must include at least one Admin View  
to be valid and compile correctly. This ensures that your component manages data  
within Joomla's native MVC architecture — offering full CRUD capabilities out-of-the-box.

---
### Why Are Admin Views Important?
Admin Views serve as the **data anchor** for the component:

- Link directly to Joomla database tables
- Automatically attach multiple fields and manage field visibility/edit permissions
- Enable subforms (linking to other Admin Views) for nested data structures
- Respect Joomla's ACL per view and field
- Reusable across multiple components — compile-safe with namespace awareness

This makes Admin Views the heart of every component, defining its schema, edit experience,  
and administrative backbone. Unlike Custom Admin Views or Site Views (which focus more on layout or data rendering),  
Admin Views define the **structural data definition** and baseline logic.

---
### Versioning and Sharing
When you need to update Admin Views in any JCB project:

- Select the views to update
- Click **"Reset"** to pull the latest version from this repository
- Or **Fork** this repository and point your JCB instance to your fork

This ensures maintainability while still allowing total customization per project.

>Admin Views are the schema-defining force in JCB — not just a UI pattern, but a declaration of how your component should structure and manage its data. We recommend exploring the shipped demo component to see Admin Views in action.

---
### Index of Admin Views


 - **Cities** | [Details](src/admin_view/3dbb581b-619a-4fb0-a6f6-e4a136ea31e2) | [Settings](src/admin_view/3dbb581b-619a-4fb0-a6f6-e4a136ea31e2/item.json) | Cities
 - **Country** | [Details](src/admin_view/6acc4069-1c33-4470-85a6-07bc9bb16d10) | [Settings](src/admin_view/6acc4069-1c33-4470-85a6-07bc9bb16d10/item.json) | A list of countries.
 - **Details (look)** | [Details](src/admin_view/595ba2c9-21fa-43a4-9af7-93c9cfb21b82) | [Settings](src/admin_view/595ba2c9-21fa-43a4-9af7-93c9cfb21b82/item.json) | Add More Details
 - **File Types (demo-look)** | [Details](src/admin_view/19a973ea-cdfa-4c79-bbbd-1b8a37286b27) | [Settings](src/admin_view/19a973ea-cdfa-4c79-bbbd-1b8a37286b27/item.json) | File Type
 - **Files** | [Details](src/admin_view/224eb9c7-8b40-48cf-bf77-2afa291fd54a) | [Settings](src/admin_view/224eb9c7-8b40-48cf-bf77-2afa291fd54a/item.json) | Files
 - **Greetings (system name)** | [Details](src/admin_view/65116558-be67-4931-95be-727fbfb16db7) | [Settings](src/admin_view/65116558-be67-4931-95be-727fbfb16db7/item.json) | Greetings
 - **Importer Message Logs** | [Details](src/admin_view/ab2bbdfc-c0a0-4ffc-9556-67d5af8bec64) | [Settings](src/admin_view/ab2bbdfc-c0a0-4ffc-9556-67d5af8bec64/item.json) | Importer Message Logs
 - **Item Import** | [Details](src/admin_view/a9f19a16-fadb-44ea-a9b6-41130aad05ec) | [Settings](src/admin_view/a9f19a16-fadb-44ea-a9b6-41130aad05ec/item.json) | Item Import Queue
 - **Look** | [Details](src/admin_view/c1053952-8a84-4398-aef1-41726f7c0043) | [Settings](src/admin_view/c1053952-8a84-4398-aef1-41726f7c0043/item.json) | The demo view
 - **Regions** | [Details](src/admin_view/9eefa86b-6294-4512-8d62-979abf16c00d) | [Settings](src/admin_view/9eefa86b-6294-4512-8d62-979abf16c00d/item.json) | Regions
 - **States** | [Details](src/admin_view/6c6345a1-e3e4-4840-8918-831034e95b19) | [Settings](src/admin_view/6c6345a1-e3e4-4840-8918-831034e95b19/item.json) | States
 - **Sub-Regions** | [Details](src/admin_view/2e451812-45af-4015-aa0c-f5912702c9af) | [Settings](src/admin_view/2e451812-45af-4015-aa0c-f5912702c9af/item.json) | Subregions
 - **Timezone** | [Details](src/admin_view/75061367-79c2-4d5b-a75d-eca6d33507df) | [Settings](src/admin_view/75061367-79c2-4d5b-a75d-eca6d33507df/item.json) | Timezones.
 - **User Entity Map** | [Details](src/admin_view/60b7b30d-9229-4ce2-b055-9efbb7ac4cea) | [Settings](src/admin_view/60b7b30d-9229-4ce2-b055-9efbb7ac4cea/item.json) | User Entity Maps

### All used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")