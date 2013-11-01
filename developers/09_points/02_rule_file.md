Points rule files are pretty identical to the achievement rule files. It uses the same json syntax and it contains enough metadata for the point rules. Similar to achievements, there are currently 2 ways for administrator's to install these rule files:

1. via Discovery method. All you need to do is to place these files in the following folder:

	`/administrator/components/com_yourcomponent/`

2. via Installation method. If you do not want to include it in your component or if you don't have a component folder, you can simply zip up the rule files in a single zip file and send it to the customer.

## Rule File Format
Every rule file must end with the extension of `.points` . If your rule file does not end with this extension, it would not be discovered or installed by the component.

Since it is a json formatted rule file, you may include one or more rules in an array as illustrated below:

Single Rule:
```php
[
	{
		"title"			: "Install Applications",
		"alias"			: "install-apps",
		"description"	: "Earn points when you install applications for your profile.",
		"command"		: "apps.install",
		"extension"		: "com_easysocial",
		"state"			: true,
		"points"		: 5
	}
]
```

Multiple Rules:

```php
[
	{
		"title"			: "Install Applications",
		"alias"			: "install-apps",
		"description"	: "Earn points when you install applications for your profile.",
		"command"		: "apps.install",
		"extension"		: "com_easysocial",
		"state"			: true,
		"points"		: 5
	},
	{
		"title"			: "Uninstall Applications",
		"alias"			: "uninstall-apps",
		"description"	: "Demote points when you uninstall applications for your profile.",
		"command"		: "apps.uninstall",
		"extension"		: "com_easysocial",
		"state"			: true,
		"points"		: -5
	}
]
```

<a href="/files/developers/multiple_points_sample.zip" class="btn btn-success"><i class="icon-info-sign"></i> &nbsp; Download Example</a>
