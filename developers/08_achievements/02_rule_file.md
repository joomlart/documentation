Achievement rule files are basically just simple json syntax and it contains enough metadata about the badge. There are currently 2 ways for administrator's to install these rule files:

1. via Discovery method. All you need to do is to place these files in the following folder:

	`/administrator/components/com_yourcomponent/`

2. via Installation method. If you do not want to include it in your component or if you don't have a component folder, you can simply zip up the rule files in a single zip file and send it to the customer.

## Rule File Format
Every rule file must end with the extension of `.badge` . If your rule file does not end with this extension, it would not be discovered or installed by the component.

Since it is a json formatted rule file, you may include one or more rules in an array as illustrated below:

Single Rule:
```php
[
	{
		// The title of the badge.
		"title" 		: "Badge Title",

		// The description of the badge
		"description"	: "Some description of your badge",

		// The steps needed to unlock this badge.
		"howto"			: "To unlock this badge, you need to do something.",

		// The alias of the badge.
		"alias"			: "socializer",

		// The extension for this badge.
		"extension"		: "com_easysocial",

		// The badge command.
		"command"		: "conversation.create",

		// The default avatar for this rule. Relative to the site's document root a.k.a (JPATH_ROOT)
		"avatar"		: "media/com_easysocial/badges/socializer.png",

		// When user creates a new discussion for 15 times.
		"frequency"		: 15
	}
]
```

Multiple Rules:

```php
[
	{
		// The title of the badge.
		"title" 		: "Badge Title",

		// The description of the badge
		"description"	: "Some description of your badge",

		// The steps needed to unlock this badge.
		"howto"			: "To unlock this badge, you need to do something.",

		// The alias of the badge.
		"alias"			: "socializer",

		// The extension for this badge.
		"extension"		: "com_easysocial",

		// The badge command.
		"command"		: "conversation.create",

		// The default avatar for this rule. Relative to the site's document root a.k.a (JPATH_ROOT)
		"avatar"		: "media/com_easysocial/badges/socializer.png",

		// When user creates a new discussion for 15 times.
		"frequency"		: 15
	},
	{
		// The title of the badge.
		"title" 		: "My Second Badge",

		// The description of the badge
		"description"	: "Some description of your badge",

		// The steps needed to unlock this badge.
		"howto"			: "To unlock this badge, you need to do something.",

		// The alias of the badge.
		"alias"			: "second",

		// The extension for this badge.
		"extension"		: "com_easysocial",

		// The badge command.
		"command"		: "second.badeg",

		// The default avatar for this rule. Relative to the site's document root a.k.a (JPATH_ROOT)
		"avatar"		: "media/com_easysocial/badges/second.png",

		// When user creates a new discussion for 15 times.
		"frequency"		: 5
	}
]
```

<a href="/files/developers/multiple_badge_sample.zip" class="btn btn-success"><i class="icon-info-sign"></i> &nbsp; Download Example</a>
