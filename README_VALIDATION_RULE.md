# JCB! Validation Rules

### What Are Validation Rules?
Validation Rules are the **guardrails** of every Joomla Component Builder (JCB) project.

They control **data integrity**, **security**, and **business logic enforcement** through the **fields** of your entire component.

Validation Rules ensure that what enters your system through a field is **correct**, **expected**, and **trusted** — before it reaches the database, file system, or application logic.

Each Validation Rule:
- Defines how a field value is **validated** and when it is considered **invalid**
- Can normalize or transform field data before it is accepted
- Integrates into Joomla's form validation system at the field level
- Is reusable across many fields, forms, and views
- Encapsulates business rules in one central, maintainable place

### Where Are Validation Rules Used in JCB?
Validation Rules in JCB link to **fields**, and only to fields whose **fieldtypes support validation**
(e.g. `textarea`, `editor`, and other validation-enabled types).

Wherever that field is used in JCB, the linked Validation Rule is automatically applied:
- ✅ **Admin Forms** (backend editing views)
- ✅ **Frontend Forms** (site-facing input)
- ✅ **Component Configurations** (parameter integrity)
- ✅ **Model Save Operations** (last gate before persistence)
- ✅ **Custom Forms & Logic** (where Form/JCB integration is used)

Validation Rules are not visual; they operate at the **data level**, wherever a field has a rule assigned.

### What Can a Validation Rule Do?
A Validation Rule in JCB is a **self-contained logic unit** that can:

- **Enforce Data Type or Structure**
  - Ensure values behave as: `string`, `integer`, `float`, `email`, `url`, etc.
  - Validate patterns like UUIDs, slugs, or IDs

- **Check Format & Constraints**
  - Enforce minimum/maximum length
  - Restrict allowed characters (e.g., alphanumeric only)
  - Validate formats (email, URL, date-like strings, JSON-encoded structures, and more)

- **Apply Business Logic**
  - Enforce that a value is unique in a specific context
  - Require that a field is only valid when another condition is met
  - Reject values that break domain-specific rules

- **Normalize / Transform Values**
  - Trim whitespace
  - Convert case (lowercase/uppercase)
  - Sanitize or clean up user input before use

- **Return Clear Failure States**
  - Mark the value as invalid
  - Provide a validation error message (often via language strings)
  - Prevent the form from being saved until the issue is resolved

This makes Validation Rules a powerful way to **centralize and standardize** how your data is allowed into the system.

### Reuse and Sharing
Validation Rules are **standalone, reusable entities**:

- Define a rule once → reuse across:
  - Multiple fields in the same component
  - Different views (admin/site)
  - Configuration forms and custom forms
- Share rules by:
  - Exporting them via repositories
  - Including them in JCB-based packages
  - Syncing from remote definitions

Because JCB wires rules into generated code and XML automatically:

- You avoid duplicating the same validation logic in multiple places.
- You maintain **consistency** across forms, views, and contexts.

This reduces maintenance overhead and keeps your validation **centralized and predictable**.
### Versioning and Customization
To update a Validation Rule:

- Use JCB's **init, reset, and push** features (if you maintain rules in a repo).
- Adjust and **rebuild** components to propagate changes.
- Optionally **fork** a rule:
  - Create a stricter or more specialized variant.
  - Keep legacy behavior for older fields while newer fields use the updated rule.

> Validation Rules turn raw input into reliable data — they ensure that every saved value respects the rules of your domain.

---
### Index of Validation Rules


 - **guid** | [Details](src/validation_rule/guid) | [Settings](src/validation_rule/guid/item.json)

### All used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")