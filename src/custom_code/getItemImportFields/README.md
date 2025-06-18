### JCB! Custom Code
# helper::getItemImportFields

## JCB (manual)
```
[CUSTOMCODE=getItemImportFields]
```

### Code
```php
	/**
	 * The Spreadsheet Headers
	 *
	 * @var   array
	 * @since 5.0.2
	 */
	protected static array $SpreadsheetHeaders = [];

	/**
	 * The Item Import Fields
	 *
	 * @var   array
	 * @since 5.0.2
	 */
	protected static array $ItemImportFields = [];

	/**
	 * Get the list of headers to show in column field
	 *
	 * @return  array  The list of headers
	 * @since   5.0.2
	 */
	public static function getSpreadsheetHeaders(): array
	{
		$endColumn = 'DA';
		$column = 'A';
		$options = [];
		while ($column !== $endColumn)
		{
			$options[$column] = self::getSpreadsheetHeader($column);
			$column = ++$column;
		}
		return $options;
	}

	/**
	 * Get the header column value (name)
	 *
	 * @return  string  The header value
	 * @since   5.0.2
	 */
	protected static function getSpreadsheetHeader(string $column): string
	{
		return self::$SpreadsheetHeaders[$column] ?? $column;
	}

	/**
	 * Set the header column values
	 *
	 * @return  void
	 * @since   5.0.2
	 */
	public static function setSpreadsheetHeaders(array $headers): void
	{
		self::$SpreadsheetHeaders = $headers;
	}

	/**
	 * Retrieves a list of import fields from the item entity.
	 *
	 * @param bool  $simple The switch to return simple list (to leave out the link data)
	 *
	 * @return array Returns an associative array where the key is the table.column name and the value 
	 *                           is the label of the column (potentially including additional information).
	 * @since  5.0.2
	 */
	public static function getItemImportFields(bool $simple = false): array
	{
		if (!empty(self::$ItemImportFields))
		{
			return self::$ItemImportFields;
		}
[[[arg0]]]
		self::$ItemImportFields = self::getImportFields($parent, $tables, $simple);

		return self::$ItemImportFields;
	}

	/**
	 * Retrieves a list of target fields from the specified tables, with appropriate filtering based on
	 * rules like ignoring certain columns, linking rules, and user roles.
	 *
	 * @param string $parent The parent entity to check for upstream linking.
	 * @param array  $tables An associative array of tables and whether to add GUID for each table. 
	 *                           The keys represent table names, and the values are booleans to indicate
	 *                           whether to include the 'guid' column.
	 * @param bool  $simple The switch to return simple list (to leave out the link data)
	 *
	 * @return array Returns an associative array where the key is the table.column name and the value 
	 *                           is the label of the column (potentially including additional information).
	 * @since  5.0.2
	 */
	protected static function getImportFields(string $parent, array $tables, bool $simple = false): array
	{
		// Get the current user object.
		$user = Joomla___39403062_84fb_46e0_bac4_0023f766e827___Power::getUser();

		$ignore = [];
		$target_fields = [];

		// Loop through each table provided.
		foreach ($tables as $table => $add_guid)
		{
			// Retrieve the fields for the table. If no fields, default to an empty array.
			$items = Super___ff8d5fdb_2d1f_4178_bd18_a43b8efd1068___Power::_('Table')->fields($table, false, true) ?? [];

			// Process each field if the table contains any fields.
			foreach ($items as $item)
			{
				$field_name = $item['name'];

				// Ignore downstream linking columns.
				if (isset($ignore[$table][$field_name]))
				{
					continue;
				}

				// Skip adding the 'guid' field if the table doesn't require it.
				if ($field_name === 'guid' && !$add_guid)
				{
					continue;
				}

				// Skip fields [ add more field you would like to skip in all targeted tables ]
				if ([[[arg1]]]$field_name === 'access' ||
					$field_name === 'metadata' ||
					$field_name === 'metakey' ||
					$field_name === 'metadesc' )
				{
					continue;
				}

				// Initialize additional info to be appended to the field label.
				$info = ' - ' . $table . '->' . $field_name . ':' . strtolower($item['db']['type']);

				// Handle linking information if available.
				if (!empty($item['link']['entity']) &&
					!empty($item['link']['value']) &&
					!empty($item['link']['key']))
				{
					
					// Ignore upstream linking columns.
					if (isset($ignore[$item['link']['entity']][$item['link']['key']]))
					{
						continue;
					}

					// Skip parent linkers for non-parent tables.
					if ($table !== $parent && $item['link']['entity'] === $parent)
					{
						continue;
					}

					$info .= ' >>> ' . $item['link']['entity'] . '->[' . $item['link']['value'] . ']->' . $item['link']['key'];
					$ignore[$item['link']['entity']] = $item['link']['key'];
				}

				if ($simple)
				{
					$target_fields[$table . '.' . $field_name] = Text::_($item['label']);
				}
				else
				{
					// For other users, append the additional field info.
					$target_fields[$table . '.' . $field_name] = Text::_($item['label']) . $info;
				}

				// Mark the current field as ignored for future checks.
				$ignore[$table][$field_name] = true;
			}
		}

		return $target_fields;
	}

	/**
	 * Retrieves a dynamic values of the import subform for item mapping
	 *
	 * @return array|null the values
	 * @since  5.0.2
	 */
	public static function getItemImportSubformValues(): ?array
	{
		$subform_name = 'maps';
		$values = [];
		$headers = self::getSpreadsheetHeaders();
		$target_fields = self::getItemImportFields();
		$number = 0;
		foreach ($headers as $header => $text)
		{
			$values["{$subform_name}{$number}"] = ['column' => $header, 'target' => self::getImportFieldMatch($text, $target_fields)];
			$number++;
		}
		return $values;
	}

	/**
	 * Matches a name value against the keys and values of a given array.
	 * The key must match strictly (===) and the value must start with the name (case-insensitive).
	 *
	 * @param string $name   The name to search for.
	 * @param array  $fields The array of fields to match against. The array should have keys and values.
	 *
	 * @return string|null Returns the key if a match is found, or null if no match is found.
	 * @since  5.0.2
	 */
	protected static function getImportFieldMatch(string $name, array $fields): string
	{
		foreach ($fields as $key => $value)
		{
			// Check if the name strictly matches the key
			if ($key === $name)
			{
				return $key;
			}

			// Check if the name starts with the value (case-insensitive)
			if (self::startsWithIgnoreCase($value, $name . ' '))
			{
				return $key;
			}
		}

		// Return null if no match is found
		return '';
	}

	/**
	 * Helper function to check if a string starts with another string (case-insensitive).
	 *
	 * @param string $haystack  The string to check.
	 * @param string $needle    The string to match the beginning.
	 *
	 * @return bool Returns true if $needle matches the start of $haystack, false otherwise.
	 * @since  5.0.2
	 */
	protected static function startsWithIgnoreCase(string $haystack, string $needle): bool
	{
		return stripos($haystack, $needle) === 0;
	}
```

> Add clean, self-contained code into your components with this reusable custom-code snippet designed for seamless integration and easy updates in JCB.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")