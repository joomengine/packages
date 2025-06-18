### JCB! Layout
# Input

## Key:
```php
echo LayoutHelper::render('input', [?]);
```

## PHP:
```php
// Extract all keys from $displayData as individual variables.
extract($displayData);

// Assign default values for variables that might not be present in $displayData.

// The 'id' parameter, defaulting to an empty string if not set or is null.
$id ??= '';

// The 'name' parameter, defaulting to 'id' if not set. Additionally, replace hyphens with underscores.
$name ??= $id;
$name = str_replace('-', '_', $name);

// The 'value' parameter, defaulting to an empty string if not set or is null.
$value ??= '';

// The 'class' parameter, defaulting to 'uk-input' if not set or is null.
$class ??= 'uk-input';

// The 'class_other' parameter, prepended with a space if set, otherwise defaulting to an empty string.
$class_other = isset($class_other) ? ' ' . $class_other : '';

// The 'placeholder' parameter, defaulting to an empty string if not set or is null.
$placeholder ??= '';

// The 'type' parameter, defaulting to 'text' if not set or is null.
$type ??= 'text';

// The 'readonly' attribute, set to 'readonly' if true, otherwise left as an empty string.
$readonly = !empty($readonly) ? ' readonly' : '';

// The 'format' attribute, added only if set, otherwise left as an empty string.
$format = !empty($format) ? ' format="' . $format . '"' : '';

// The 'onchange' attribute, added only if set, otherwise left as an empty string.
$onchange = isset($onchange) ? ' onchange="' . $onchange . '"' : '';

// The 'onkeydown' attribute, added only if set, otherwise left as an empty string.
$onkeydown = isset($onkeydown) ? ' onkeydown="' . $onkeydown . '"' : '';

// The 'required' attribute, set to 'required' if true, otherwise left as an empty string.
$required = !empty($required) ? ' required' : '';
```

## HTML:
```html
<input
	class="<?php echo $class . $class_other; ?>"
	name="<?php echo $name; ?>"
	id="<?php echo $id; ?>"
	type="<?php echo $type; ?>"
	placeholder="<?php echo $placeholder; ?>"
	value="<?php echo $value; ?>"
	<?php echo $readonly; echo $onchange; echo $onkeydown; echo $format; echo $required; ?>
>
```

> Enhance your Joomla components with a reusable layout that ensures consistent design, easy updates, and full compatibility within the JCB framework.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")