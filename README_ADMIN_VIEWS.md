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


 - **Address** | [Details](src/admin_view/b7b2aba5-8a94-443b-814b-aed5b0b7c550) | [Settings](src/admin_view/b7b2aba5-8a94-443b-814b-aed5b0b7c550/item.json) | Addresses of Members
 - **Address Types** | [Details](src/admin_view/5992077e-15a5-4ea9-b882-e6e0e1b723ae) | [Settings](src/admin_view/5992077e-15a5-4ea9-b882-e6e0e1b723ae/item.json) | Types of Addresses
 - **Addresses (eHealth)** | [Details](src/admin_view/5349e968-76e0-42db-b7a3-b99019c8d32d) | [Settings](src/admin_view/5349e968-76e0-42db-b7a3-b99019c8d32d/item.json) | Addresses of Members
 - **Administration Part** | [Details](src/admin_view/95a834f5-59e8-4f1d-93a6-13479b2148f0) | [Settings](src/admin_view/95a834f5-59e8-4f1d-93a6-13479b2148f0/item.json) | Administration Part Admin View
 - **Antenatal Care** | [Details](src/admin_view/a4da86a9-e165-4a90-a73e-ca9956884c00) | [Settings](src/admin_view/a4da86a9-e165-4a90-a73e-ca9956884c00/item.json) | Antenatal Care Admin View
 - **Breast Cancer** | [Details](src/admin_view/d9a2f539-f13d-4d39-ab36-b258162f39b7) | [Settings](src/admin_view/d9a2f539-f13d-4d39-ab36-b258162f39b7/item.json) | Breast Cancer Admin view
 - **Cervical Cancer** | [Details](src/admin_view/82ca091d-e00d-4378-a780-fafaf084d98a) | [Settings](src/admin_view/82ca091d-e00d-4378-a780-fafaf084d98a/item.json) | Cervical Cancer Admin view
 - **Cities** | [Details](src/admin_view/3dbb581b-619a-4fb0-a6f6-e4a136ea31e2) | [Settings](src/admin_view/3dbb581b-619a-4fb0-a6f6-e4a136ea31e2/item.json) | Cities
 - **Cities (eHealth)** | [Details](src/admin_view/b878bb81-45df-495f-b84e-3abee0a694db) | [Settings](src/admin_view/b878bb81-45df-495f-b84e-3abee0a694db/item.json) | Cities
 - **Clinic** | [Details](src/admin_view/a970eed5-0f6c-4a46-ac51-0667dcb5e38e) | [Settings](src/admin_view/a970eed5-0f6c-4a46-ac51-0667dcb5e38e/item.json) | Clinic Admin View
 - **Counseling Type** | [Details](src/admin_view/bc34bf73-580d-4c2b-9cb5-d705c52a1dc6) | [Settings](src/admin_view/bc34bf73-580d-4c2b-9cb5-d705c52a1dc6/item.json) | Counseling Type Admin View
 - **Country** | [Details](src/admin_view/6acc4069-1c33-4470-85a6-07bc9bb16d10) | [Settings](src/admin_view/6acc4069-1c33-4470-85a6-07bc9bb16d10/item.json) | A list of countries.
 - **Country (eHealth)** | [Details](src/admin_view/e4fc2180-5a15-46f7-bb40-921f494b8d3a) | [Settings](src/admin_view/e4fc2180-5a15-46f7-bb40-921f494b8d3a/item.json) | A list of countries.
 - **Dependent** | [Details](src/admin_view/2ad66e35-e5fc-4927-a76d-edd00746543e) | [Settings](src/admin_view/2ad66e35-e5fc-4927-a76d-edd00746543e/item.json) | Dependents of Members
 - **Details (look)** | [Details](src/admin_view/595ba2c9-21fa-43a4-9af7-93c9cfb21b82) | [Settings](src/admin_view/595ba2c9-21fa-43a4-9af7-93c9cfb21b82/item.json) | Add More Details
 - **Diagnosis Type** | [Details](src/admin_view/588139bf-7c03-48ed-bcb0-3832a14bd553) | [Settings](src/admin_view/588139bf-7c03-48ed-bcb0-3832a14bd553/item.json) | Diagnosis Type Admin View
 - **Family Planning** | [Details](src/admin_view/2bf85986-5ed4-4471-88fe-a5b2daa9114f) | [Settings](src/admin_view/2bf85986-5ed4-4471-88fe-a5b2daa9114f/item.json) | Family Planning Admin View
 - **File Types (demo-look)** | [Details](src/admin_view/19a973ea-cdfa-4c79-bbbd-1b8a37286b27) | [Settings](src/admin_view/19a973ea-cdfa-4c79-bbbd-1b8a37286b27/item.json) | File Type
 - **File Types (eHealth)** | [Details](src/admin_view/aef94ff0-6877-4b72-83ef-f50644b639d8) | [Settings](src/admin_view/aef94ff0-6877-4b72-83ef-f50644b639d8/item.json) | File Type
 - **Files** | [Details](src/admin_view/224eb9c7-8b40-48cf-bf77-2afa291fd54a) | [Settings](src/admin_view/224eb9c7-8b40-48cf-bf77-2afa291fd54a/item.json) | Files
 - **Files (eHealth)** | [Details](src/admin_view/7fdcbc56-76af-43c3-9955-3f291c5adfdb) | [Settings](src/admin_view/7fdcbc56-76af-43c3-9955-3f291c5adfdb/item.json) | Files
 - **Foetal Engagement** | [Details](src/admin_view/30a8a740-b413-43f2-aacf-3c16903d4e76) | [Settings](src/admin_view/30a8a740-b413-43f2-aacf-3c16903d4e76/item.json) | Foetal Engagement Admin View
 - **Foetal Lie** | [Details](src/admin_view/8181ea02-be0a-475e-99c6-c7d84817959c) | [Settings](src/admin_view/8181ea02-be0a-475e-99c6-c7d84817959c/item.json) | Foetal Lie Admin View
 - **Foetal Presentation** | [Details](src/admin_view/ee0dc737-9d72-4af2-a5a9-095d092d9cea) | [Settings](src/admin_view/ee0dc737-9d72-4af2-a5a9-095d092d9cea/item.json) | Foetal Presentation Admin View
 - **General Medical Check Up** | [Details](src/admin_view/81100e6f-5535-41ca-94f6-cc2fcbf75e1e) | [Settings](src/admin_view/81100e6f-5535-41ca-94f6-cc2fcbf75e1e/item.json) | General Medical Check Up
 - **Greetings (system name)** | [Details](src/admin_view/65116558-be67-4931-95be-727fbfb16db7) | [Settings](src/admin_view/65116558-be67-4931-95be-727fbfb16db7/item.json) | Greetings
 - **HIV Counseling and Testing** | [Details](src/admin_view/b28c4fc2-fae5-4866-9859-e64bad07ab6b) | [Settings](src/admin_view/b28c4fc2-fae5-4866-9859-e64bad07ab6b/item.json) | HIV Counseling and Testing
 - **Health Education** | [Details](src/admin_view/4206aef4-c8f9-4288-889d-ac9aee23e1dd) | [Settings](src/admin_view/4206aef4-c8f9-4288-889d-ac9aee23e1dd/item.json) | Health Education Admin View
 - **Health Education Topic** | [Details](src/admin_view/4689d234-151f-4122-8cd3-d7b92f17f5e1) | [Settings](src/admin_view/4689d234-151f-4122-8cd3-d7b92f17f5e1/item.json) | Health Education Topic Admin View
 - **Immunisation** | [Details](src/admin_view/c53406eb-99f0-4491-ad57-b8e5d81f1613) | [Settings](src/admin_view/c53406eb-99f0-4491-ad57-b8e5d81f1613/item.json) | Immunisation Admin View
 - **Immunisation Type** | [Details](src/admin_view/16b889b9-1bad-4642-be14-d8e216283c22) | [Settings](src/admin_view/16b889b9-1bad-4642-be14-d8e216283c22/item.json) | Immunisation Type Admin View
 - **Immunisation Vaccine Type** | [Details](src/admin_view/ccc3cca7-2ef6-49ff-aba9-02588e80cd23) | [Settings](src/admin_view/ccc3cca7-2ef6-49ff-aba9-02588e80cd23/item.json) | Immunisation Vaccine Type Admin View
 - **Importer Message Logs** | [Details](src/admin_view/ab2bbdfc-c0a0-4ffc-9556-67d5af8bec64) | [Settings](src/admin_view/ab2bbdfc-c0a0-4ffc-9556-67d5af8bec64/item.json) | Importer Message Logs
 - **Ingredient** | [Details](src/admin_view/0cd962eb-6b6c-49c6-a49b-bc96fb310609) | [Settings](src/admin_view/0cd962eb-6b6c-49c6-a49b-bc96fb310609/item.json) | Ingredient
 - **Item Import** | [Details](src/admin_view/a9f19a16-fadb-44ea-a9b6-41130aad05ec) | [Settings](src/admin_view/a9f19a16-fadb-44ea-a9b6-41130aad05ec/item.json) | Item Import Queue
 - **Look** | [Details](src/admin_view/c1053952-8a84-4398-aef1-41726f7c0043) | [Settings](src/admin_view/c1053952-8a84-4398-aef1-41726f7c0043/item.json) | The demo view
 - **Look (demo-J6)** | [Details](src/admin_view/93a34bf3-aa25-4a14-8496-ae7d0340e0b9) | [Settings](src/admin_view/93a34bf3-aa25-4a14-8496-ae7d0340e0b9/item.json) | The main demo view
 - **Medication** | [Details](src/admin_view/d412bc8c-4e9d-4cdf-b248-a64df06381ff) | [Settings](src/admin_view/d412bc8c-4e9d-4cdf-b248-a64df06381ff/item.json) | Medication Admin View
 - **NonPay Reason** | [Details](src/admin_view/b2522e43-69df-4f70-b2c3-b15dcfeb7578) | [Settings](src/admin_view/b2522e43-69df-4f70-b2c3-b15dcfeb7578/item.json) | NonPay Reason Admin View
 - **Patients** | [Details](src/admin_view/48c6102c-f2bb-4350-869e-d7afa9649e5c) | [Settings](src/admin_view/48c6102c-f2bb-4350-869e-d7afa9649e5c/item.json) | Patients of the Health Portal
 - **Payment** | [Details](src/admin_view/72f86056-268d-4d75-b0a6-dcf6ba3e8ad9) | [Settings](src/admin_view/72f86056-268d-4d75-b0a6-dcf6ba3e8ad9/item.json) | Payment Admin View
 - **Payment Type** | [Details](src/admin_view/6b20b2c4-3888-4d6c-91d4-872ae6223f4d) | [Settings](src/admin_view/6b20b2c4-3888-4d6c-91d4-872ae6223f4d/item.json) | Payment Type Admin View
 - **Planning Type** | [Details](src/admin_view/39f9de66-43ab-4d9a-9bda-7f1b8815807d) | [Settings](src/admin_view/39f9de66-43ab-4d9a-9bda-7f1b8815807d/item.json) | Planning Type Admin View
 - **Prostate and Testicular Cancer** | [Details](src/admin_view/72a4776e-889b-4324-ba5a-cdc8184e2b34) | [Settings](src/admin_view/72a4776e-889b-4324-ba5a-cdc8184e2b34/item.json) | Prostate and Testicular Cancer Admin view
 - **Recipe** | [Details](src/admin_view/7f969e93-a96a-4a4f-8307-b6a9de06bda2) | [Settings](src/admin_view/7f969e93-a96a-4a4f-8307-b6a9de06bda2/item.json) | Recipe
 - **Referral** | [Details](src/admin_view/956bb320-40ea-4995-b046-cb647eec4aa9) | [Settings](src/admin_view/956bb320-40ea-4995-b046-cb647eec4aa9/item.json) | Referral Admin View
 - **Regions** | [Details](src/admin_view/9eefa86b-6294-4512-8d62-979abf16c00d) | [Settings](src/admin_view/9eefa86b-6294-4512-8d62-979abf16c00d/item.json) | Regions
 - **Regions (eHealth)** | [Details](src/admin_view/6a512b3e-a9e6-494a-ba7a-6b718cdf5007) | [Settings](src/admin_view/6a512b3e-a9e6-494a-ba7a-6b718cdf5007/item.json) | Regions
 - **Site** | [Details](src/admin_view/51d1b057-47b2-4a41-a2f5-7eafb4e46d7a) | [Settings](src/admin_view/51d1b057-47b2-4a41-a2f5-7eafb4e46d7a/item.json) | Site Admin View
 - **States** | [Details](src/admin_view/6c6345a1-e3e4-4840-8918-831034e95b19) | [Settings](src/admin_view/6c6345a1-e3e4-4840-8918-831034e95b19/item.json) | States
 - **States (eHealth)** | [Details](src/admin_view/33cfd25b-6e35-41de-bfc2-902921291b0c) | [Settings](src/admin_view/33cfd25b-6e35-41de-bfc2-902921291b0c/item.json) | States
 - **Strength** | [Details](src/admin_view/b93c838d-4dd0-4931-90e8-81138a2ae106) | [Settings](src/admin_view/b93c838d-4dd0-4931-90e8-81138a2ae106/item.json) | Strength Admin View
 - **Sub-Regions** | [Details](src/admin_view/2e451812-45af-4015-aa0c-f5912702c9af) | [Settings](src/admin_view/2e451812-45af-4015-aa0c-f5912702c9af/item.json) | Subregions
 - **Sub-Regions (eHealth)** | [Details](src/admin_view/30898a86-be83-4d2e-8392-756c64ee8f04) | [Settings](src/admin_view/30898a86-be83-4d2e-8392-756c64ee8f04/item.json) | Subregions
 - **Test** | [Details](src/admin_view/88b75034-c158-4651-9fd2-555a1a8249c4) | [Settings](src/admin_view/88b75034-c158-4651-9fd2-555a1a8249c4/item.json) | Test Admin view
 - **Testing Reason** | [Details](src/admin_view/61fec258-5dd0-48ae-a9c1-8b2de0686a23) | [Settings](src/admin_view/61fec258-5dd0-48ae-a9c1-8b2de0686a23/item.json) | Testing Reason Admin View
 - **Timezone** | [Details](src/admin_view/75061367-79c2-4d5b-a75d-eca6d33507df) | [Settings](src/admin_view/75061367-79c2-4d5b-a75d-eca6d33507df/item.json) | Timezones.
 - **Timezone (eHealth)** | [Details](src/admin_view/b2b10dc7-0848-4d29-97d3-e886ee8141dc) | [Settings](src/admin_view/b2b10dc7-0848-4d29-97d3-e886ee8141dc/item.json) | Timezones.
 - **Tuberculosis** | [Details](src/admin_view/f67497fa-7c34-4574-84c9-e479dd37475f) | [Settings](src/admin_view/f67497fa-7c34-4574-84c9-e479dd37475f/item.json) | Tuberculosis
 - **Units** | [Details](src/admin_view/b549040e-9f87-472d-801e-ca9859e1a4c4) | [Settings](src/admin_view/b549040e-9f87-472d-801e-ca9859e1a4c4/item.json) | Units Admin View
 - **User Entity Map** | [Details](src/admin_view/60b7b30d-9229-4ce2-b055-9efbb7ac4cea) | [Settings](src/admin_view/60b7b30d-9229-4ce2-b055-9efbb7ac4cea/item.json) | User Entity Maps
 - **VMMC** | [Details](src/admin_view/2cbd9486-089b-45b8-8f1a-8161e9f88a5c) | [Settings](src/admin_view/2cbd9486-089b-45b8-8f1a-8161e9f88a5c/item.json) | VMMC Admin View
 - **eHealth User Entity Map** | [Details](src/admin_view/e9251e1e-80b7-43e7-84a0-6d890d05ed28) | [Settings](src/admin_view/e9251e1e-80b7-43e7-84a0-6d890d05ed28/item.json) | User Entity Maps

### All used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")