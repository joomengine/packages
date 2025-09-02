### JCB! Custom Code
# helper::fancyDate($date)

## JCB (manual)
```
[CUSTOMCODE=niceFancyDate]
```

### Code
```php
	/**
	 * Convert a date to a human-readable fancy format (e.g., "1st of January 2024").
	 *
	 * @param string|int  $date         The date as a string or timestamp.
	 * @param bool        $checkStamp   Whether to check if the input is a timestamp.
	 *
	 * @return string Formatted date.
	 * @since 3.0.0
	 * @deprecated 4.0.0 Use Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::fancyDate($date, $checkStamp);
	 */
	public static function fancyDate($date, bool $checkStamp = true): string
	{
		return Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::fancyDate($date, $checkStamp);
	}

	/**
	 * Get a formatted date based on the time period (dynamic format based on age of the date).
	 *
	 * @param string|int  $date         The date as a string or timestamp.
	 * @param bool        $checkStamp   Whether to check if the input is a timestamp.
	 *
	 * @return string Formatted date.
	 * @since 3.0.0
	 * @deprecated 4.0.0 Use Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::fancyDynamicDate($date, $checkStamp);
	 */
	public static function fancyDynamicDate($date, bool $checkStamp = true): string
	{
		return Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::fancyDynamicDate($date, $checkStamp);
	}

	/**
	 * Convert a date to a human-readable day, time, and date format (e.g., "Mon 12am 1st of January 2024").
	 *
	 * @param string|int  $date         The date as a string or timestamp.
	 * @param bool        $checkStamp   Whether to check if the input is a timestamp.
	 *
	 * @return string Formatted day, time, and date.
	 * @since 3.0.0
	 * @deprecated 4.0.0 Use Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::fancyDayTimeDate($date, $checkStamp);
	 */
	public static function fancyDayTimeDate($date, bool $checkStamp = true): string
	{
		return Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::fancyDayTimeDate($date, $checkStamp);
	}

	/**
	 * Convert a date to a human-readable time and date format (e.g., "(12:00) 1st of January 2024").
	 *
	 * @param string|int  $date         The date as a string or timestamp.
	 * @param bool        $checkStamp   Whether to check if the input is a timestamp.
	 *
	 * @return string Formatted time and date.
	 * @since 3.0.0
	 * @deprecated 4.0.0 Use Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::fancyDateTime($date, $checkStamp);
	 */
	public static function fancyDateTime($date, bool $checkStamp = true): string
	{
		return Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::fancyDateTime($date, $checkStamp);
	}

	/**
	 * Convert a time to a human-readable format (e.g., "12:00").
	 *
	 * @param string|int  $date         The date as a string or timestamp.
	 * @param bool        $checkStamp   Whether to check if the input is a timestamp.
	 *
	 * @return string Formatted time.
	 * @since 3.0.0
	 * @deprecated 4.0.0 Use Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::fancyTime($date, $checkStamp);
	 */
	public static function fancyTime($date, bool $checkStamp = true): string
	{
		return Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::fancyTime($date, $checkStamp);
	}

	/**
	 * Convert a date to the day name (e.g., "Sunday").
	 *
	 * @param string|int  $date         The date as a string or timestamp.
	 * @param bool        $checkStamp   Whether to check if the input is a timestamp.
	 *
	 * @return string Day name.
	 * @since 3.0.0
	 * @deprecated 4.0.0 Use Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::setDayName($date, $checkStamp);
	 */
	public static function setDayName($date, bool $checkStamp = true): string
	{
		return Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::setDayName($date, $checkStamp);
	}

	/**
	 * Convert a date to the month name (e.g., "January").
	 *
	 * @param string|int  $date         The date as a string or timestamp.
	 * @param bool        $checkStamp   Whether to check if the input is a timestamp.
	 *
	 * @return string Month name.
	 * @since 3.0.0
	 * @deprecated 4.0.0 Use Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::setMonthName($date, $checkStamp);
	 */
	public static function setMonthName($date, bool $checkStamp = true): string
	{
		return Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::setMonthName($date, $checkStamp);
	}

	/**
	 * Convert a date to the day with suffix (e.g., "1st").
	 *
	 * @param string|int  $date         The date as a string or timestamp.
	 * @param bool        $checkStamp   Whether to check if the input is a timestamp.
	 *
	 * @return string Day with suffix.
	 * @since 3.0.0
	 * @deprecated 4.0.0 Use Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::setDay($date, $checkStamp);
	 */
	public static function setDay($date, bool $checkStamp = true): string
	{
		return Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::setDay($date, $checkStamp);
	}

	/**
	 * Convert a date to the numeric month (e.g., "5").
	 *
	 * @param string|int  $date         The date as a string or timestamp.
	 * @param bool        $checkStamp   Whether to check if the input is a timestamp.
	 *
	 * @return string Numeric month.
	 * @since 3.0.0
	 * @deprecated 4.0.0 Use Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::setMonth($date, $checkStamp);
	 */
	public static function setMonth($date, bool $checkStamp = true): string
	{
		return Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::setMonth($date, $checkStamp);
	}

	/**
	 * Convert a date to the full year (e.g., "2024").
	 *
	 * @param string|int  $date         The date as a string or timestamp.
	 * @param bool        $checkStamp   Whether to check if the input is a timestamp.
	 *
	 * @return string Full year.
	 * @since 3.0.0
	 * @deprecated 4.0.0 Use Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::setYear($date, $checkStamp);
	 */
	public static function setYear($date, bool $checkStamp = true): string
	{
		return Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::setYear($date, $checkStamp);
	}

	/**
	 * Convert a date to a year/month format (e.g., "2024/05").
	 *
	 * @param string|int  $date         The date as a string or timestamp.
	 * @param string      $spacer       The spacer between year and month.
	 * @param bool        $checkStamp   Whether to check if the input is a timestamp.
	 *
	 * @return string Year/Month format.
	 * @since 3.0.0
	 * @deprecated 4.0.0 Use Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::setYearMonth($date, $spacer, $checkStamp);
	 */
	public static function setYearMonth($date, string $spacer = '/', bool $checkStamp = true): string
	{
		return Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::setYearMonth($date, $spacer, $checkStamp);
	}

	/**
	 * Convert a date to a year/month/day format (e.g., "2024/05/03").
	 *
	 * @param string|int  $date         The date as a string or timestamp.
	 * @param string      $spacer       The spacer between year and month.
	 * @param bool        $checkStamp   Whether to check if the input is a timestamp.
	 *
	 * @return string Year/Month/Day format.
	 * @since 3.0.0
	 * @deprecated 4.0.0 Use Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::setYearMonthDay($date, $spacer, $checkStamp);
	 */
	public static function setYearMonthDay($date, string $spacer = '/', bool $checkStamp = true): string
	{
		return Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::setYearMonthDay($date, $spacer, $checkStamp);
	}

	/**
	 * Convert a date to a day/month/year format (e.g., "03/05/2024").
	 *
	 * @param string|int  $date         The date as a string or timestamp.
	 * @param string      $spacer       The spacer between year and month.
	 * @param bool        $checkStamp   Whether to check if the input is a timestamp.
	 *
	 * @return string Day/Month/Year format.
	 * @since 3.0.0
	 * @deprecated 4.0.0 Use Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::setDayMonthYear($date, $spacer, $checkStamp);
	 */
	public static function setDayMonthYear($date, string $spacer = '/', bool $checkStamp = true): string
	{
		return Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::setDayMonthYear($date, $spacer, $checkStamp);
	}

	/**
	 * Convert a date string to a valid timestamp.
	 *
	 * @param string|int  $date         The date as a string or timestamp.
	 * @param bool        $checkStamp   Whether to check if the input is a timestamp.
	 *
	 * @return int The valid timestamp.
	 * @since 3.0.0
	 * @deprecated 4.0.0 Use Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::getValidTimestamp($date, $checkStamp);
	 */
	public static function getValidTimestamp($date, bool $checkStamp): int
	{
		return Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::getValidTimestamp($date, $checkStamp);
	}

	/**
	 * Check if the input is a valid Unix timestamp.
	 *
	 * @param mixed $timestamp The timestamp to validate.
	 *
	 * @return bool True if valid timestamp, false otherwise.
	 * @since 3.0.0
	 * @deprecated 4.0.0 Use Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::isValidTimeStamp($timestamp);
	 */
	public static function isValidTimeStamp($timestamp): bool
	{
		return Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::isValidTimeStamp($timestamp);
	}

	/**
	 * Check if a string is a valid date according to the specified format.
	 *
	 * @param string $date The date string to validate.
	 * @param string $format The format to check against (default is 'Y-m-d H:i:s').
	 *
	 * @return bool True if valid date, false otherwise.
	 * @since 3.0.0
	 * @deprecated 4.0.0 Use Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::isValidateDate($date, $format);
	 */
	public static function isValidateDate($date, string $format = 'Y-m-d H:i:s'): bool
	{
		return Super___993fe913_8e36_4800_a5f7_544aa728ee48___Power::isValidateDate($date, $format);
	}
```

> Add clean, self-contained code into your components with this reusable custom-code snippet designed for seamless integration and easy updates in JCB.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")