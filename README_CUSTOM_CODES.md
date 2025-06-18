# JCB! Custom Codes

### What Are Custom Codes in JCB?
Custom Codes in JCB allow you to create and manage custom logic that can be reused, shared, and even injected  
into your component code at compile time. This feature supports **two advanced use cases**:

1. **Reusable Code Blocks with Argument Injection**
	called: **JCB (manual)**
2. **Persistent File Modification via Insert/Replace Tags**
	called: **Hash (automation)**

---
### 1. Reusable Code Injection with `[CUSTOMCODE=...]` (JCB manual)
This method allows you to define a custom code block once and inject it into any JCB-supported code area  
using a placeholder like:

```text
[CUSTOMCODE=mainReadmePackageFooter]
````

You can also pass **dynamic arguments** into these placeholders:

```text
[CUSTOMCODE=mainReadmePackageFooter+foo,bar,baz]
```

Your custom code may then reference these values using zero-based placeholders:

* `[[[arg0]]]` → `foo`
* `[[[arg1]]]` → `bar`
* `[[[arg2]]]` → `baz`

If your code uses `n` placeholders, **you must pass `n` arguments** during use.

> 🧠 **Encoding Special Characters:**
> To include reserved characters in arguments, use these HTML-safe equivalents:
> `[` ⇒ `&#91;`   `]` ⇒ `&#93;`   `,` ⇒ `&#44;`   `+` ⇒ `&#43;`   `=` ⇒ `&#61;`

#### Scope of Use:

* Works in any JCB code area (PHP, JS, HTML, etc.)
* Can be used **within other custom codes**
* ❗ **Cannot be used inside its own definition or in IDE hash automation code**

#### Note on Editor Sync:

At present, argument-based custom codes **cannot be reversed back from the compiled project into the UI**
without losing the `[[[argX]]]` placeholders. All updates for such code **must be done via the JCB UI**
until this limitation is resolved.

---
### 2. Persistent File Overrides via Insert/Replace Tags (Hash automation)
When working with a compiled component installed on the same Joomla instance as JCB,
you can **insert or replace blocks of code** inside the actual generated files using special comment tags like:

```php
/***[INSERT<>$$$$]***/
// your code
/***[/INSERT<>$$$$]***/
```

JCB scans for these tags and:

* Extracts the content
* Stores it in the Custom Code UI
* Keeps track of the file and line number
* Re-injects the code on future compilations

This works for both **PHP** and **HTML** using appropriately formatted tag styles.

If the injection location becomes ambiguous, JCB will:

* Comment out the custom code block
* Warn you about the issue
* Preserve the code for manual review

📘 Full tag syntax reference available here:
👉 [TIPS: Custom Code](https://git.vdm.dev/joomla/Component-Builder/wiki/TIPS:-Custom-Code)

---
### 3. Reverse Engineering of Language Strings
When custom code uses `Text::_('SOME_CONSTANT')` language strings, JCB automatically converts them
**back into their readable string form** when importing into the editor. This improves maintainability
by letting you work with the original values rather than language constants.

---
### 4. Customization, Forking, and Version Control
As with other JCB entities, Custom Codes support a Git-based workflow:

* **Init**: Import from a repository
* **Reset**: Overwrite with the repository version
* **Push**: Update a shared repository if you have write access
* **Fork**: Maintain and manage your own custom code set

This design encourages collaborative and modular development across multiple JCB projects.

---
### Index of Custom Codes


 - **Database Schema Check (call)** | [Details](src/custom_code/databaseSchemaCheckCall) | [Settings](src/custom_code/databaseSchemaCheckCall/item.json) | JCB (manual)
 - **FormController Edit Method** | [Details](src/custom_code/formControllerEdit) | [Settings](src/custom_code/formControllerEdit/item.json) | JCB (manual)
 - **README - Contributors 2 JCB** | [Details](src/custom_code/readMEcontributors) | [Settings](src/custom_code/readMEcontributors/item.json) | JCB (manual)
 - **Set GUID in Form (power)** | [Details](src/custom_code/setGUIDFormPower) | [Settings](src/custom_code/setGUIDFormPower/item.json) | JCB (manual)
 - **Unlock the Power of Joomla! Development** | [Details](src/custom_code/unlockThePowerOfJoomlaDevelopment) | [Settings](src/custom_code/unlockThePowerOfJoomlaDevelopment/item.json) | JCB (manual)
 - **addUikitThreeToAdminViews** | [Details](src/custom_code/addUikitThreeToAdminViews) | [Settings](src/custom_code/addUikitThreeToAdminViews/item.json) | JCB (manual)
 - **helper::fancyDate($date)** | [Details](src/custom_code/niceFancyDate) | [Settings](src/custom_code/niceFancyDate/item.json) | JCB (manual)
 - **helper::getItemImportFields** | [Details](src/custom_code/getItemImportFields) | [Settings](src/custom_code/getItemImportFields/item.json) | JCB (manual)
 - **php Configuration Check (call)** | [Details](src/custom_code/phpConfigurationCheckCall) | [Settings](src/custom_code/phpConfigurationCheckCall/item.json) | JCB (manual)
 - **save GUID (Power)** | [Details](src/custom_code/saveGUIDPower) | [Settings](src/custom_code/saveGUIDPower/item.json) | JCB (manual)
 - **vdmUploaderConfig** | [Details](src/custom_code/vdmUploaderConfig) | [Settings](src/custom_code/vdmUploaderConfig/item.json) | JCB (manual)

### All used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")