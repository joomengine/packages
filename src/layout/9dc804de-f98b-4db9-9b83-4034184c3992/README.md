### JCB! Layout
# Joomla! Mastodon Feed

## Key:
```php
echo LayoutHelper::render('mastodon', [?]);
```

## PHP:
```php
// Extract all keys from $displayData as individual variables.
extract($displayData ?? []);

// Default fallback values
$defaultValues = [
	[ // Llewellyn
		'account' => '112766899254600077',
		'instance' => 'https://joomla.social',
		'invite_url' => 'https://joomla.social/invite/gzAvC48K',
		'invite_heading' => Text::_("Llewellyn's Joomla! Social Feed"),
		'invite_title' => Text::_("Join JCB's lead developer on Joomla! social a Mastodon instance.")
//	], // removed since the feed is inactive at this time. if active, we can add it back in.
//	[ // Joomla
//		'account' => '112755435087541569',
//		'instance' => 'https://joomla.social',
//		'invite_url' => 'https://joomla.social/invite/PCXktw8g',
//		'invite_heading' => Text::_("Joomla! Social Feed"),
//		'invite_title' => Text::_("Join Joomla! social a Mastodon instance!")
	]
];

// List of default accounts
$defaultAccounts ??= $defaultValues;

// function to retrieve active account
$getActiveAccount = function ($accounts, array $defaults): object {
	if (!empty($accounts) && is_array($accounts)) {
		// Select a random account and return it as an object
		return (object) $accounts[array_rand($accounts)];
	}
	// Return defaults as an object if no accounts are available
	return (object) $defaults;
};

// Get the active account
$activeAccount = $getActiveAccount($defaultAccounts, $defaultValues[0]);

// Assign values

// The 'id' parameter, defaulting to mastodon-feed.
$id ??= 'mastodon-feed';

// The button 'id' parameter, defaulting to refresh-feed.
$button_id ??= 'refresh-feed';

// The number of post to load
$posts ??= 5;

// The URL of the Mastodon instance to use; defaults to the instance of the selected account.
$instance ??= $activeAccount->instance;

// The unique account ID for the selected Mastodon account; defaults to the ID of the selected account.
$account ??= $activeAccount->account;

// The invitation URL for the Mastodon instance, used to invite others to join; defaults to the invite URL of the selected account.
$invite_url ??= $activeAccount->invite_url;

// The heading displayed for the invitation; defaults to the invite heading of the selected account.
$invite_heading ??= $activeAccount->invite_heading;

// The title displayed for the invitation; defaults to the invite title of the selected account.
$invite_title ??= $activeAccount->invite_title;
```

## HTML:
```html
<div  class="well well-small mastadon-display-block">
	<h2>
		<a
			href="<?php echo $invite_url; ?>"
			title="<?php echo $invite_title; ?>">
				<?php echo $invite_heading; ?>
		</a>&nbsp;&nbsp;
		<a
			type="button"
			id="<?php echo $button_id; ?>"
			href="#"
			title="<?php echo Text::_('Refresh Feed'); ?>">
				<i class="icon-loop"></i>
		</a>
	</h2>
	<div id="<?php echo $id; ?>"
		data-instance="<?php echo $instance; ?>"
		data-account-id="<?php echo $account; ?>"
		data-post-count="<?php echo $posts; ?>">
	</div>
	<script>
		new MastodonFeed("<?php echo $id; ?>", "<?php echo $button_id; ?>");
	</script>
</div>
```

> Enhance your Joomla components with a reusable layout that ensures consistent design, easy updates, and full compatibility within the JCB framework.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")