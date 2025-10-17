### JCB! Field
# Type (custom)

> Field Type: Custom

## Field XML:
```xml
<field
	type="addresstype"
	name="type"
	label="Type"
	description="Specifies the purpose of the address, such as billing, shipping, or registered location."
	class="list_class"
	layout="joomla.form.field.list-fancy-select"
	multiple="false"
	required="true"
	extends="list"
	button="false"
	table="#__###component###_address_type"
	component="com_###component###"
	entity="###view###"
	view="type"
	views="types"
	value_field="name"
	key_field="guid"
	prime_php="1"
	type_php_1="__.o0=base64=Oo.__CQkvLyBHZXQgdGhlIGRhdGFic2Ugb2JqZWN0Lg0KCQkkZGIgPSBGYWN0b3J5OjpnZXREQk8oKTsNCgkJJHF1ZXJ5ID0gJGRiLT5nZXRRdWVyeSh0cnVlKTsNCgkJJHF1ZXJ5LT5zZWxlY3QoJGRiLT5xdW90ZU5hbWUoYXJyYXkoJ2EuIyMjSUQjIyMnLCdhLiMjI1RFWFQjIyMnKSxhcnJheSgnIyMjSUQjIyMnLCcjIyNDT0RFX1RFWFQjIyMnKSkpOw0KCQkkcXVlcnktPmZyb20oJGRiLT5xdW90ZU5hbWUoJyMjI1RBQkxFIyMjJywgJ2EnKSk7DQoJCSRxdWVyeS0+d2hlcmUoJGRiLT5xdW90ZU5hbWUoJ2EucHVibGlzaGVkJykgLiAnID0gMScpOw0KCQkkcXVlcnktPm9yZGVyKCdhLiMjI1RFWFQjIyMgQVNDJyk7DQoJCSRkYi0+c2V0UXVlcnkoKHN0cmluZykkcXVlcnkpOw0KCQkkaXRlbXMgPSAkZGItPmxvYWRPYmplY3RMaXN0KCk7DQoJCSRvcHRpb25zID0gW107DQoJCWlmICgkaXRlbXMpDQoJCXsNCgkJCWlmICgkdGhpcy0+bXVsdGlwbGUgPT09IGZhbHNlKQ0KCQkJew0KCQkJCSRvcHRpb25zW10gPSBIdG1sOjpfKCdzZWxlY3Qub3B0aW9uJywgJycsIFRleHQ6Ol8oJ1NlbGVjdCBhbiBvcHRpb24nKSk7DQoJCQl9DQoJCQlmb3JlYWNoKCRpdGVtcyBhcyAkaXRlbSkNCgkJCXsNCgkJCQkkb3B0aW9uc1tdID0gSHRtbDo6Xygnc2VsZWN0Lm9wdGlvbicsICRpdGVtLT4jIyNJRCMjIywgJGl0ZW0tPiMjI0NPREVfVEVYVCMjIyk7DQoJCQl9DQoJCX0NCgkJcmV0dXJuICRvcHRpb25zOw=="
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