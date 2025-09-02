# JCB! Fields

### What Are Fields?
Fields are the **foundation** of every Joomla Component Builder (JCB) project.

They define how data is **stored**, **validated**, **rendered**, and **interacted with** in your Joomla extensions.

Fields let you control everything from the **underlying database schema** to the **user interface**, all within a single configuration.

Each Field:
- Defines **database structure** (type, size, default, null, unique keys, indexes)
- Binds to a **fieldtype**, determining HTML rendering and behavior
- Supports per-field **custom PHP** for model saving and retrieval
- Allows styling and scripting (HTML attributes, JS, CSS)
- Automatically generates Joomla-compliant XML field definitions

### Where Are Fields Used in JCB?
Fields are universal integrated — they are used in, highly structured areas:

- ✅ **Admin Views** (the native Joomla back-end editing views)
- ✅ **Modules** (frontend display configurations)
- ✅ **Plugins** (event-driven integrations)
- ✅ **Component Configurations** (global parameter settings)

### What Can a Field Do?
A Field in JCB can define:

- **Database Type & Schema**: `int`, `varchar`, `json`, custom, nullable, defaults, indexes
- **Permissions**: who can view/edit the field (ACL)
- **Rendering Options**: HTML classes, labels, JS behaviors
- **Model Integration**: how the value is saved or retrieved
- **Dynamic Logic**: PHP hooks for `onGet`, `onSave`, `onPrepareForm`, etc.
- **Fieldtypes**: link to rich behaviors like Model Selects, Subforms, Toggle Switches, Encrypted Fields, etc.

This centralization makes field management efficient and highly reusable.

### Reuse and Sharing
Fields are standalone entities:

- Define once, **reuse across multiple Admin Views**, Modules, or Plugins
- Fields can also be exported and shared via repositories
- JCB will automatically adjust them to fit into each consuming context

This means less duplication, and greater consistency across your entire component structure.

### Versioning and Customization
To update a field:

- Click **"reset"** in the JCB UI to sync with this repository
- Or **fork** this repository, customize the field, and point JCB to your fork

This preserves version control while allowing your own field improvements to live independently.

>Fields define both structure and behavior — they are where your data comes alive.

---
### Index of Fields


 - **Abbreviation (demo)** | [Details](src/field/c35e18fa-cade-48b8-b067-6289cc7a0f60) | [Settings](src/field/c35e18fa-cade-48b8-b067-6289cc7a0f60/item.json)
 - **Alias** | [Details](src/field/335866ce-b81b-4329-901d-c20254135c9c) | [Settings](src/field/335866ce-b81b-4329-901d-c20254135c9c/item.json)
 - **Allowed Document Formats** | [Details](src/field/24f17aaf-cc19-4bad-bc8b-4d37c79a898d) | [Settings](src/field/24f17aaf-cc19-4bad-bc8b-4d37c79a898d/item.json)
 - **Allowed File Formats** | [Details](src/field/ca8f38cb-f930-4976-a76b-c1d6cd18652d) | [Settings](src/field/ca8f38cb-f930-4976-a76b-c1d6cd18652d/item.json)
 - **Allowed Image Formats** | [Details](src/field/6b3c73d5-7640-43c0-a2e7-125a187f4513) | [Settings](src/field/6b3c73d5-7640-43c0-a2e7-125a187f4513/item.json)
 - **Allowed Media Formats** | [Details](src/field/fd936809-37c1-4016-a4ee-a4d016343725) | [Settings](src/field/fd936809-37c1-4016-a4ee-a4d016343725/item.json)
 - **Allowed Type** | [Details](src/field/9f6f776f-9741-4aec-a3ff-fb9880fdcb5c) | [Settings](src/field/9f6f776f-9741-4aec-a3ff-fb9880fdcb5c/item.json)
 - **Branch Height** | [Details](src/field/f8ceaba3-04d3-406d-abb9-c8372100817c) | [Settings](src/field/f8ceaba3-04d3-406d-abb9-c8372100817c/item.json)
 - **Capital (citites-modal)** | [Details](src/field/baeaf484-f61b-4688-8b8a-e3ace669b7a7) | [Settings](src/field/baeaf484-f61b-4688-8b8a-e3ace669b7a7/item.json)
 - **Cities (state)** | [Details](src/field/6630c034-f87f-4c5c-ab72-e5ae0e4c0e5b) | [Settings](src/field/6630c034-f87f-4c5c-ab72-e5ae0e4c0e5b/item.json)
 - **Code Three (currency)** | [Details](src/field/59f0d051-768e-41de-87a0-f47551f7d0d1) | [Settings](src/field/59f0d051-768e-41de-87a0-f47551f7d0d1/item.json)
 - **Column** | [Details](src/field/6a17f5e4-d21e-47f1-9b92-493ab725d55f) | [Settings](src/field/6a17f5e4-d21e-47f1-9b92-493ab725d55f/item.json)
 - **Confirm Password2** | [Details](src/field/27c39335-cd12-46a5-82e7-26d3c67b9bb6) | [Settings](src/field/27c39335-cd12-46a5-82e7-26d3c67b9bb6/item.json)
 - **Countries (multisubform)** | [Details](src/field/4d96ceea-7dd1-45c3-86fd-0d73d66332a8) | [Settings](src/field/4d96ceea-7dd1-45c3-86fd-0d73d66332a8/item.json)
 - **Country (modal)** | [Details](src/field/8d1b9d7e-77c1-43d9-bc97-0dd021bfe779) | [Settings](src/field/8d1b9d7e-77c1-43d9-bc97-0dd021bfe779/item.json)
 - **Crop Details** | [Details](src/field/6f327030-dcdf-4d80-b3d9-293d4bbe39f7) | [Settings](src/field/6f327030-dcdf-4d80-b3d9-293d4bbe39f7/item.json)
 - **Crop Height (in pixels)** | [Details](src/field/ab0d3b92-bd90-4957-ab71-cbc7a5fabeb3) | [Settings](src/field/ab0d3b92-bd90-4957-ab71-cbc7a5fabeb3/item.json)
 - **Crop Width (in pixels)** | [Details](src/field/1616608c-5307-4496-89e2-36a326a84716) | [Settings](src/field/1616608c-5307-4496-89e2-36a326a84716/item.json)
 - **Currency Name (country)** | [Details](src/field/4b964b88-36b4-4f26-a828-0e798ce9af38) | [Settings](src/field/4b964b88-36b4-4f26-a828-0e798ce9af38/item.json)
 - **Date of Birth (not required)** | [Details](src/field/c8cc2a22-f2e4-4dcc-9088-ed1d78416228) | [Settings](src/field/c8cc2a22-f2e4-4dcc-9088-ed1d78416228/item.json)
 - **Default Text Colour** | [Details](src/field/7414d14b-b802-4ac2-9090-218cdb32156c) | [Settings](src/field/7414d14b-b802-4ac2-9090-218cdb32156c/item.json)
 - **Description (full width)** | [Details](src/field/749a9917-90c3-49c4-9e72-aa33b0683a87) | [Settings](src/field/749a9917-90c3-49c4-9e72-aa33b0683a87/item.json)
 - **Download Access** | [Details](src/field/794ac8d4-c78b-4f98-9953-07e4ce5ad491) | [Settings](src/field/794ac8d4-c78b-4f98-9953-07e4ce5ad491/item.json)
 - **Email (not required)** | [Details](src/field/976f7e2d-68e3-497e-b4d1-6326d5b95078) | [Settings](src/field/976f7e2d-68e3-497e-b4d1-6326d5b95078/item.json)
 - **Email (required)** | [Details](src/field/10c1eccb-b3c3-4325-a056-45a72d116fd8) | [Settings](src/field/10c1eccb-b3c3-4325-a056-45a72d116fd8/item.json)
 - **End of Life Background Colour** | [Details](src/field/f83befac-e15e-421c-83a0-c17e99492b79) | [Settings](src/field/f83befac-e15e-421c-83a0-c17e99492b79/item.json)
 - **End of Life Text Colour** | [Details](src/field/8097f524-48e6-470a-aa42-e4383d3019fa) | [Settings](src/field/8097f524-48e6-470a-aa42-e4383d3019fa/item.json)
 - **Entity File Type** | [Details](src/field/2a877e46-59b9-4f97-9dec-8c84c16741f2) | [Settings](src/field/2a877e46-59b9-4f97-9dec-8c84c16741f2/item.json)
 - **Entity Type (Hidden)** | [Details](src/field/8a64b899-6cb9-4ba3-bed1-559675f8d20b) | [Settings](src/field/8a64b899-6cb9-4ba3-bed1-559675f8d20b/item.json)
 - **Entity Type (demo)** | [Details](src/field/2e24a9fe-5793-46be-b071-631c0b18d8f4) | [Settings](src/field/2e24a9fe-5793-46be-b071-631c0b18d8f4/item.json)
 - **FIPS code** | [Details](src/field/fa0ead84-06c8-4f18-89ae-4cdf646fd961) | [Settings](src/field/fa0ead84-06c8-4f18-89ae-4cdf646fd961/item.json)
 - **File (Importer)** | [Details](src/field/91939b1a-c4d6-4531-8356-63bc4ca243fb) | [Settings](src/field/91939b1a-c4d6-4531-8356-63bc4ca243fb/item.json)
 - **File Extension** | [Details](src/field/080b92dc-a4b4-46b2-83d4-3430284f5e06) | [Settings](src/field/080b92dc-a4b4-46b2-83d4-3430284f5e06/item.json)
 - **File Name** | [Details](src/field/725e856a-b8cc-4590-90e3-3eed6fd0873c) | [Settings](src/field/725e856a-b8cc-4590-90e3-3eed6fd0873c/item.json)
 - **File Path** | [Details](src/field/ed28e30c-30c3-4830-afdc-5a61bf25cd49) | [Settings](src/field/ed28e30c-30c3-4830-afdc-5a61bf25cd49/item.json)
 - **File Size** | [Details](src/field/77a1711b-ad1f-4379-921b-5e4ef5c31a42) | [Settings](src/field/77a1711b-ad1f-4379-921b-5e4ef5c31a42/item.json)
 - **File Type** | [Details](src/field/c2f884f9-31a0-4bb9-8310-64b5d9132d32) | [Settings](src/field/c2f884f9-31a0-4bb9-8310-64b5d9132d32/item.json)
 - **Flag emoji (country flag)** | [Details](src/field/962ec39f-78d4-42ee-9626-7b778d2eea25) | [Settings](src/field/962ec39f-78d4-42ee-9626-7b778d2eea25/item.json)
 - **Flag emojiU (unicode for flag)** | [Details](src/field/b71ee1ab-78ea-4cc7-aa2e-490a4d01a03f) | [Settings](src/field/b71ee1ab-78ea-4cc7-aa2e-490a4d01a03f/item.json)
 - **Footer Height** | [Details](src/field/fb71c5cc-65d9-4389-8599-b94f4eecc97c) | [Settings](src/field/fb71c5cc-65d9-4389-8599-b94f4eecc97c/item.json)
 - **Future Background Colour** | [Details](src/field/8f485452-b062-4ec9-9fa5-0182d04d8d7c) | [Settings](src/field/8f485452-b062-4ec9-9fa5-0182d04d8d7c/item.json)
 - **Future Text Colour** | [Details](src/field/1805a9da-75bf-41d6-b120-4c021fd93d8d) | [Settings](src/field/1805a9da-75bf-41d6-b120-4c021fd93d8d/item.json)
 - **GMT Offset Name (timezone)** | [Details](src/field/480c9734-2820-4a61-afea-75b1db3fadc9) | [Settings](src/field/480c9734-2820-4a61-afea-75b1db3fadc9/item.json)
 - **GMT Offset Seconds (timezone)** | [Details](src/field/17788601-b3f8-439e-8ad7-11c7f8109e22) | [Settings](src/field/17788601-b3f8-439e-8ad7-11c7f8109e22/item.json)
 - **GUID** | [Details](src/field/5aa57bbe-7b19-4db9-915c-561863458d2b) | [Settings](src/field/5aa57bbe-7b19-4db9-915c-561863458d2b/item.json)
 - **GUID (Hidden)** | [Details](src/field/fb3115a1-e579-401a-9b53-9469cd4739e4) | [Settings](src/field/fb3115a1-e579-401a-9b53-9469cd4739e4/item.json)
 - **GUID ENTITY** | [Details](src/field/3f1fedeb-b943-42a7-88e7-c4f1eb1fd8a4) | [Settings](src/field/3f1fedeb-b943-42a7-88e7-c4f1eb1fd8a4/item.json)
 - **Greeting** | [Details](src/field/75e830a6-a3a5-4327-9161-3f774a6f1591) | [Settings](src/field/75e830a6-a3a5-4327-9161-3f774a6f1591/item.json)
 - **Header Height** | [Details](src/field/3d3bf310-a38f-4e31-89c8-d5d986f4bb53) | [Settings](src/field/3d3bf310-a38f-4e31-89c8-d5d986f4bb53/item.json)
 - **ISO Three (country)** | [Details](src/field/95f46f99-0909-4a47-879b-ede06ef35fb8) | [Settings](src/field/95f46f99-0909-4a47-879b-ede06ef35fb8/item.json)
 - **ISO Two (country)** | [Details](src/field/2039d1c3-162c-401c-96fe-f127683ee3fe) | [Settings](src/field/2039d1c3-162c-401c-96fe-f127683ee3fe/item.json)
 - **Import Status** | [Details](src/field/11698dc6-8ff6-4662-b3b7-e47494463a08) | [Settings](src/field/11698dc6-8ff6-4662-b3b7-e47494463a08/item.json)
 - **Latitude (decimal)** | [Details](src/field/f7d3d78e-2d35-4884-a997-d073f853d095) | [Settings](src/field/f7d3d78e-2d35-4884-a997-d073f853d095/item.json)
 - **Legend Background Colour** | [Details](src/field/8f1c9c1f-9d64-4f6c-9066-777665c7dcac) | [Settings](src/field/8f1c9c1f-9d64-4f6c-9066-777665c7dcac/item.json)
 - **Legend Text Colour** | [Details](src/field/11bf8b86-99ad-4003-82eb-c55c16d0a041) | [Settings](src/field/11bf8b86-99ad-4003-82eb-c55c16d0a041/item.json)
 - **Longitude (decimal)** | [Details](src/field/09c22738-6c6f-48ca-a24d-d439757e8619) | [Settings](src/field/09c22738-6c6f-48ca-a24d-d439757e8619/item.json)
 - **Look Groups** | [Details](src/field/104f8410-a07e-4cf8-aad5-2b4db7c6864c) | [Settings](src/field/104f8410-a07e-4cf8-aad5-2b4db7c6864c/item.json)
 - **Map** | [Details](src/field/2d0566ab-cfbe-4ca2-8d05-8e2c70eda191) | [Settings](src/field/2d0566ab-cfbe-4ca2-8d05-8e2c70eda191/item.json)
 - **Margin Left** | [Details](src/field/12ecc6cc-9195-4633-8ecd-27ecc0643bd4) | [Settings](src/field/12ecc6cc-9195-4633-8ecd-27ecc0643bd4/item.json)
 - **Margin Right** | [Details](src/field/3e72e2ab-0731-46f1-83ac-8bffddcd5634) | [Settings](src/field/3e72e2ab-0731-46f1-83ac-8bffddcd5634/item.json)
 - **Max Years** | [Details](src/field/9f5ddbec-3f1c-4af9-8d33-a158bcaaf453) | [Settings](src/field/9f5ddbec-3f1c-4af9-8d33-a158bcaaf453/item.json)
 - **Message Status** | [Details](src/field/0f4fa86e-25a8-4bbf-91a3-7ea9790b4df8) | [Settings](src/field/0f4fa86e-25a8-4bbf-91a3-7ea9790b4df8/item.json)
 - **Messages** | [Details](src/field/c6e1e451-99b8-4e1b-aa19-c48c3513bf4f) | [Settings](src/field/c6e1e451-99b8-4e1b-aa19-c48c3513bf4f/item.json)
 - **Mime** | [Details](src/field/68c1e141-fb2e-49a6-bf56-1da6d8a058e8) | [Settings](src/field/68c1e141-fb2e-49a6-bf56-1da6d8a058e8/item.json)
 - **Min Years** | [Details](src/field/44a3a4aa-f601-4765-b656-2f0a01dd6fd9) | [Settings](src/field/44a3a4aa-f601-4765-b656-2f0a01dd6fd9/item.json)
 - **Mobile Phone (not-required)** | [Details](src/field/f40974bd-a946-4bc4-9be1-fedec2d09c24) | [Settings](src/field/f40974bd-a946-4bc4-9be1-fedec2d09c24/item.json)
 - **More Details** | [Details](src/field/d763ecd7-8d72-418e-8010-706c0785baab) | [Settings](src/field/d763ecd7-8d72-418e-8010-706c0785baab/item.json)
 - **Name (Key - Required)** | [Details](src/field/5d3d34dd-4876-4c6a-86ab-b4e162f22c08) | [Settings](src/field/5d3d34dd-4876-4c6a-86ab-b4e162f22c08/item.json)
 - **Nationality (country)** | [Details](src/field/8ba72283-32fa-4a34-8c0d-d52adfed1aa5) | [Settings](src/field/8ba72283-32fa-4a34-8c0d-d52adfed1aa5/item.json)
 - **Native (country)** | [Details](src/field/2aad92a4-895d-46cb-b0df-751da1bdd703) | [Settings](src/field/2aad92a4-895d-46cb-b0df-751da1bdd703/item.json)
 - **Note VDM File Display** | [Details](src/field/639e63b1-a63d-4d40-853f-42e7b28a5d35) | [Settings](src/field/639e63b1-a63d-4d40-853f-42e7b28a5d35/item.json)
 - **Note VDM File Uploader** | [Details](src/field/47a3db14-de87-4cc2-8724-17f437a77d93) | [Settings](src/field/47a3db14-de87-4cc2-8724-17f437a77d93/item.json)
 - **Numeric Code (currency)** | [Details](src/field/40da896f-5054-4bb2-aa58-1cdfb391f544) | [Settings](src/field/40da896f-5054-4bb2-aa58-1cdfb391f544/item.json)
 - **Password** | [Details](src/field/b9097198-705f-4a6b-bd10-676d55cd6517) | [Settings](src/field/b9097198-705f-4a6b-bd10-676d55cd6517/item.json)
 - **Phone Code (country)** | [Details](src/field/149140a8-d0a6-4b62-a880-bb796e2145d8) | [Settings](src/field/149140a8-d0a6-4b62-a880-bb796e2145d8/item.json)
 - **Region (modal)** | [Details](src/field/7f3ccb20-7c57-433a-987b-b53d801004f3) | [Settings](src/field/7f3ccb20-7c57-433a-987b-b53d801004f3/item.json)
 - **Show Legend** | [Details](src/field/dc416a4a-a19f-4ef5-a703-e2334df42efd) | [Settings](src/field/dc416a4a-a19f-4ef5-a703-e2334df42efd/item.json)
 - **State (modal)** | [Details](src/field/1e666136-800a-486d-a8e8-13a054b7acde) | [Settings](src/field/1e666136-800a-486d-a8e8-13a054b7acde/item.json)
 - **State/cities (multisubform)** | [Details](src/field/9a21f28b-b818-4cc5-b18a-c3fa33a5876d) | [Settings](src/field/9a21f28b-b818-4cc5-b18a-c3fa33a5876d/item.json)
 - **Storage Folder** | [Details](src/field/523f91f8-ca60-44f7-9de0-645549967095) | [Settings](src/field/523f91f8-ca60-44f7-9de0-645549967095/item.json)
 - **Sub-Region (modal)** | [Details](src/field/19b4a840-cf4e-4012-8fae-b1439af74f5a) | [Settings](src/field/19b4a840-cf4e-4012-8fae-b1439af74f5a/item.json)
 - **Subregions (subform)** | [Details](src/field/cb04e362-61c0-4a07-8d80-d13b6939a72c) | [Settings](src/field/cb04e362-61c0-4a07-8d80-d13b6939a72c/item.json)
 - **Symbol (currency)** | [Details](src/field/c9a4c765-a0f9-42da-8fa9-df41ab70c448) | [Settings](src/field/c9a4c765-a0f9-42da-8fa9-df41ab70c448/item.json)
 - **TLD (country)** | [Details](src/field/c4c23fad-fd03-41cc-b5db-25f60b8ee11f) | [Settings](src/field/c4c23fad-fd03-41cc-b5db-25f60b8ee11f/item.json)
 - **Target (Files)** | [Details](src/field/e24026ef-294a-48e5-9be0-3f95dcb2b66b) | [Settings](src/field/e24026ef-294a-48e5-9be0-3f95dcb2b66b/item.json)
 - **Target Field** | [Details](src/field/7d613846-8f1e-43f4-8bb9-1fcdbb473fa5) | [Settings](src/field/7d613846-8f1e-43f4-8bb9-1fcdbb473fa5/item.json)
 - **Timezone Identifier (timezone)** | [Details](src/field/c20d4692-6e97-4441-83bd-561b73730407) | [Settings](src/field/c20d4692-6e97-4441-83bd-561b73730407/item.json)
 - **Timezone Name (timezone)** | [Details](src/field/f921d762-f5f1-4811-b1f5-71840c003a4e) | [Settings](src/field/f921d762-f5f1-4811-b1f5-71840c003a4e/item.json)
 - **Timezones (country)** | [Details](src/field/c803e176-923f-43a8-a542-12e27619a5f2) | [Settings](src/field/c803e176-923f-43a8-a542-12e27619a5f2/item.json)
 - **Today Line Colour** | [Details](src/field/cb60a327-5ce5-4b48-a8e0-27321022bf40) | [Settings](src/field/cb60a327-5ce5-4b48-a8e0-27321022bf40/item.json)
 - **Today Text Colour** | [Details](src/field/a2e37110-c69f-41b3-b05b-f5f51d0d9ab4) | [Settings](src/field/a2e37110-c69f-41b3-b05b-f5f51d0d9ab4/item.json)
 - **Type (of state)** | [Details](src/field/4321fa80-702d-4ff5-ab3c-05507d3007a9) | [Settings](src/field/4321fa80-702d-4ff5-ab3c-05507d3007a9/item.json)
 - **User ID** | [Details](src/field/3dfab308-41de-4d11-9c94-4ba330a202ac) | [Settings](src/field/3dfab308-41de-4d11-9c94-4ba330a202ac/item.json)
 - **User ID (Hidden)** | [Details](src/field/a0d7c091-1781-45fb-a71f-1447bad69614) | [Settings](src/field/a0d7c091-1781-45fb-a71f-1447bad69614/item.json)
 - **Username (required)** | [Details](src/field/b7edbefd-d8ee-4765-9a09-ab1922e70e68) | [Settings](src/field/b7edbefd-d8ee-4765-9a09-ab1922e70e68/item.json)
 - **Users** | [Details](src/field/c61285fd-2e35-4605-869f-66d2fbd70004) | [Settings](src/field/c61285fd-2e35-4605-869f-66d2fbd70004/item.json)
 - **Versions** | [Details](src/field/801520d9-b7b3-47c5-a2a9-2581199ead0b) | [Settings](src/field/801520d9-b7b3-47c5-a2a9-2581199ead0b/item.json)
 - **Website (no required)** | [Details](src/field/6c3a6983-d1bf-4e5e-9e99-deea00b0cefd) | [Settings](src/field/6c3a6983-d1bf-4e5e-9e99-deea00b0cefd/item.json)
 - **WikiDataId** | [Details](src/field/af59b3ac-6a00-42c0-bbe2-edf90dec6081) | [Settings](src/field/af59b3ac-6a00-42c0-bbe2-edf90dec6081/item.json)
 - **Year Width** | [Details](src/field/a2f93b12-c3fd-4e00-9732-0c97a7f37489) | [Settings](src/field/a2f93b12-c3fd-4e00-9732-0c97a7f37489/item.json)
 - **Years Line Colour** | [Details](src/field/9e2dcfc2-ea21-4caf-88aa-f0706d5878e5) | [Settings](src/field/9e2dcfc2-ea21-4caf-88aa-f0706d5878e5/item.json)
 - **Years Text Colour** | [Details](src/field/0a6ee559-822b-4cd1-a049-d956ba2ff80b) | [Settings](src/field/0a6ee559-822b-4cd1-a049-d956ba2ff80b/item.json)

### All used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")