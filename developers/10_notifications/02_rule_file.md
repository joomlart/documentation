Every notification that needs to be generated on the site needs to require a rule file generated for it first. This is to ensure that the user is allowed to choose whether they want to be notified or not.

The alert rule files are based on JSON syntax and it's pretty easy to install them.

There are 2 methods of installing an alert rule file:

1. via Discovery method. All you need to do is to place these files in the following folder:

	`/administrator/components/com_yourcomponent/`

2. via Installation method. If you do not want to include it in your component or if you don't have a component folder, you can simply zip up the rule files in a single zip file and send it to the customer.

## Alert Rule File Format
Every rule file must end with the extension of `.alert` . If your alert rule file does not end with this extension, it would not be discovered or installed by the component.

Since it is a json formatted rule file, you may include one or more rules in an array as illustrated below:

Single Rule:
```php
[
	{
		"element"	: "likes",
		"rule"	: "item"
	}
]
```

Multiple Rules:

```php
[
	{
		"element"	: "likes",
		"rule"	: "item"
	},
	{
		"element" : "likes",
		"rule"	: "involved"
	}
]
```

<a href="/files/developers/multiple_alert_sample.zip" class="btn btn-success"><i class="icon-info-sign"></i> &nbsp; Download Example</a>
