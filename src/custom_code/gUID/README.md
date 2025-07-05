### JCB! Custom Code
# helper::GUID

## JCB (manual)
```
[CUSTOMCODE=gUID]
```

### Code
```php
	/**
	 * Returns a GUIDv4 string
	 * 
	 * Thanks to Dave Pearson (and other)
	 * https://www.php.net/manual/en/function.com-create-guid.php#119168 
	 *
	 * Uses the best cryptographically secure method
	 * for all supported platforms with fallback to an older,
	 * less secure version.
	 *
	 * @param bool $trim
	 * @return string
	 */
	public static function GUID ($trim = true)
	{
		// Windows
		if (function_exists('com_create_guid') === true)
		{
			if ($trim === true)
			{
				return trim(com_create_guid(), '{}');
			}
			return com_create_guid();
		}

		// set the braces if needed
		$lbrace = $trim ? "" : chr(123);    // "{"
		$rbrace = $trim ? "" : chr(125);    // "}"

		// OSX/Linux
		if (function_exists('openssl_random_pseudo_bytes') === true)
		{
			$data = openssl_random_pseudo_bytes(16);
			$data[6] = chr(ord($data[6]) & 0x0f | 0x40);    // set version to 0100
			$data[8] = chr(ord($data[8]) & 0x3f | 0x80);    // set bits 6-7 to 10
			return $lbrace . vsprintf('%s%s-%s-%s-%s-%s%s%s', str_split(bin2hex($data), 4)) . $lbrace;
		}

		// Fallback (PHP 4.2+)
		mt_srand((double)microtime() * 10000);
		$charid = strtolower(md5(uniqid(rand(), true)));
		$hyphen = chr(45);                  // "-"
		$guidv4 = $lbrace.
			substr($charid,  0,  8).$hyphen.
			substr($charid,  8,  4).$hyphen.
			substr($charid, 12,  4).$hyphen.
			substr($charid, 16,  4).$hyphen.
			substr($charid, 20, 12).
			$rbrace;
		return $guidv4;
	}

	/**
	 * Validate the Globally Unique Identifier ( and check if table already has this identifier)
	 *
	 * @param string $guid
	 * @param string $table
	 * @param int      $id
	 * @return bool
	 */
	public static function validGUID ($guid, $table = null, $id = 0)
	{
		// check if we have a string
		if (self::validateGUID($guid))
		{
			// check if table already has this identifier
			if (self::checkString($table))
			{
				// Get the database object and a new query object.
				$db = \JFactory::getDbo();
				$query = $db->getQuery(true);
				$query->select('COUNT(*)')
					->from('#__[[[component]]]_' . (string) $table)
					->where($db->quoteName('guid') . ' = ' . $db->quote($guid));

				// remove this item from the list
				if ($id > 0)
				{
					$query->where($db->quoteName('id') . ' <> ' . (int) $id);
				}

				// Set and query the database.
				$db->setQuery($query);
				$duplicate = (bool) $db->loadResult();

				if ($duplicate)
				{
					return false;
				}
			}
			return true;
		}
		return false;
	}

	/**
	 * get the ID of a GUID
	 *
	 * @param string $guid
	 * @param string $table
	 *
	 * @return int
	 */
	public static function getGUIDID ($guid, $table, $default = false)
	{
		// check if we have a string
		if (self::validateGUID($guid))
		{
			// check if table already has this identifier
			if (self::checkString($table))
			{
				// Get the database object and a new query object.
				$db = \JFactory::getDbo();
				$query = $db->getQuery(true);
				$query->select('id')
					->from('#__[[[component]]]_' . (string) $table)
					->where($db->quoteName('guid') . ' = ' . $db->quote($guid));

				// Set and query the database.
				$db->setQuery($query);
				$db->execute();

				if ($db->getNumRows())
				{
					return $db->loadResult();
				}
			}
		}
		return $default;
	}

	/**
	 * Validate the Globally Unique Identifier
	 *
	 * Thanks to Lewie
	 * https://stackoverflow.com/a/1515456/1429677
	 *
	 * @param string $guid
	 * @return bool
	 */
	protected static function validateGUID ($guid)
	{
		// check if we have a string
		if (self::checkString($guid))
		{
			return preg_match("/^(\{)?[a-f\d]{8}(-[a-f\d]{4}){4}[a-f\d]{8}(?(1)\})$/i", $guid);
		}
		return false;
	}

```

> Add clean, self-contained code into your components with this reusable custom-code snippet designed for seamless integration and easy updates in JCB.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")