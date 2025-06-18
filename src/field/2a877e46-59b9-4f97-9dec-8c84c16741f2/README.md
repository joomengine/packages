### JCB! Field
# Entity File Type

> Field Type: Custom

## Field XML:
```xml
<field
	type="entityfiletypes"
	name="file_type"
	label="Select Upload Type"
	class="list_class"
	layout="joomla.form.field.list-fancy-select"
	multiple="false"
	required="false"
	extends="list"
	button="false"
	table="#__###component###_file_type"
	component="com_###component###"
	entity="###view###"
	view="file_type"
	views="file_types"
	value_field="name"
	key_field="guid"
	prime_php="1"
	type_php_1="__.o0=base64=Oo.__Ly8gR2V0IHRoZSB1c2VyIG9iamVjdC4NCgkJJHVzZXIgPSBGYWN0b3J5OjpnZXRBcHBsaWNhdGlvbigpLT5nZXRJZGVudGl0eSgpOw0KCQkvLyBHZXQgdGhlIGRhdGFiYXNlIG9iamVjdC4NCgkJJGRiID0gRmFjdG9yeTo6Z2V0REJPKCk7DQoJCSRxdWVyeSA9ICRkYi0+Z2V0UXVlcnkodHJ1ZSk7DQoJCSRxdWVyeS0+c2VsZWN0KCRkYi0+cXVvdGVOYW1lKGFycmF5KCdhLiMjI0lEIyMjJywnYS4jIyNURVhUIyMjJywnYS50YXJnZXQnKSxhcnJheSgnIyMjSUQjIyMnLCcjIyNDT0RFX1RFWFQjIyMnLCd0YXJnZXQnKSkpOw0KCQkkcXVlcnktPmZyb20oJGRiLT5xdW90ZU5hbWUoJyMjI1RBQkxFIyMjJywgJ2EnKSk7DQoJCSRxdWVyeS0+d2hlcmUoJGRiLT5xdW90ZU5hbWUoJ2EucHVibGlzaGVkJykgLiAnID0gMScpOw0KCQkkcXVlcnktPm9yZGVyKCdhLiMjI1RFWFQjIyMgQVNDJyk7DQoJCS8vIEltcGxlbWVudCBWaWV3IExldmVsIEFjY2VzcyAoaWYgc2V0IGluIHRhYmxlKQ0KCQlpZiAoISR1c2VyLT5hdXRob3Jpc2UoJ2NvcmUub3B0aW9ucycsICdbW1tjb21fY29tcG9uZW50XV1dJykpDQoJCXsNCgkJCSRncm91cHMgPSBpbXBsb2RlKCcsJywgJHVzZXItPmdldEF1dGhvcmlzZWRWaWV3TGV2ZWxzKCkpOw0KCQkJJHF1ZXJ5LT53aGVyZSgnYS5hY2Nlc3MgSU4gKCcgLiAkZ3JvdXBzIC4gJyknKTsNCgkJfQ0KCQkkZGItPnNldFF1ZXJ5KChzdHJpbmcpJHF1ZXJ5KTsNCgkJJGl0ZW1zID0gJGRiLT5sb2FkT2JqZWN0TGlzdCgpOw0KCQkkZW50aXR5ID0gJHRoaXMtPmdldEF0dHJpYnV0ZSgnZW50aXR5Jyk7DQoJCSRvcHRpb25zID0gW107DQoJCWlmICgkaXRlbXMpDQoJCXsNCgkJCWlmICgkdGhpcy0+bXVsdGlwbGUgPT09IGZhbHNlKQ0KCQkJew0KCQkJCSRvcHRpb25zW10gPSBIdG1sOjpfKCdzZWxlY3Qub3B0aW9uJywgJycsIFRleHQ6Ol8oJ1NlbGVjdCBhbiBvcHRpb24nKSk7DQoJCQl9DQoJCQlmb3JlYWNoKCRpdGVtcyBhcyAkaXRlbSkNCgkJCXsNCgkJCQlpZiAoU3VwZXJfX180YjIyNWM1MV9kMjkzXzQ4ZTRfYjNmNl81MTM2Y2Y1YzNmMThfX19Qb3dlcjo6Y2hlY2soJGl0ZW0tPnRhcmdldCkpDQoJCQkJew0KCQkJCQkkaXRlbS0+dGFyZ2V0ID0ganNvbl9kZWNvZGUoJGl0ZW0tPnRhcmdldCwgdHJ1ZSk7DQoJCQkJfQ0KCQkJCWlmIChTdXBlcl9fXzBhNTljNjVjXzlkYWZfNGJjOV9iYWY0X2UwNjNmZjllNmE4YV9fX1Bvd2VyOjpjaGVjaygkaXRlbS0+dGFyZ2V0KSAmJiBpbl9hcnJheSgkZW50aXR5LCAkaXRlbS0+dGFyZ2V0KSkNCgkJCQl7DQoJCQkJCSRvcHRpb25zW10gPSBIdG1sOjpfKCdzZWxlY3Qub3B0aW9uJywgJGl0ZW0tPiMjI0lEIyMjLCAkaXRlbS0+IyMjQ09ERV9URVhUIyMjKTsNCgkJCQl9DQoJCQl9DQoJCX0NCgkJaWYgKGNvdW50KCRvcHRpb25zKSA8PSAxKQ0KCQl7DQoJCQlyZXR1cm4gW0h0bWw6Ol8oJ3NlbGVjdC5vcHRpb24nLCAnJywgVGV4dDo6c3ByaW50ZignTm8gZmlsZSB0eXBlcyBsaW5rZWQgdG8gdGhlICglcykgYXJlYS4nLCAkZW50aXR5KSldOw0KCQl9DQoJCXJldHVybiAkb3B0aW9uczs="
/>
```

## Database:
- Data type: VARCHAR
- Data length: 36
- Data default: 
- Null switch: NULL
- Index: KEY
- Modeling: Default

> Define, capture, and control data effortlessly with this Field; the core building block of every JCB component.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")