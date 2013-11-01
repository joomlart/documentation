_This is optional and only needed if the field have extra per-field-configuration or to override any default configuration_

Not to be confused with [app configuration](app_configuration), this configuration applies separately on each field instances and is not shared accross the same field added to the profile.

Each fields comes with a [default set of configuration](#default-parameters) such as Title, Description, etc. You can use this feature to define [extra configuration parameters](#extra-parameters) or [override the existing default set of configuration parameters](#override-parameters).

<a name="default-parameters"></a>
## Default parameters

These are a set of parameters that is attached to a field by default.

* title
* display_title
* description
* display_description
* default
* required
* searchable
* privacy
* visible_registration
* visible_edit
* visible_display
* unique_key

<a name="extra-parameters"></a>
## Extra parameters

You can define extra parameters that are unique to your field.

__Important! Parameter name cannot be any of the default parameters.__

To define extra parameters, create a config.json in the config folder from the root of the field:

`/config/config.json`

The configuration parameters should be defined in JSON format.

	{	
		"minimum_character": {
			"label"		: "Minimum characters",
			"tooltip"	: "Minimum character allowed",
			"type"		: "text",
			"default"	: "10"
		},
	
		"maximum_character": {
			"label"		: "Maximum characters",
			"tooltip"	: "Maximum character allowed",
			"type"		: "text",
			"default"	: 100
		}
	}

Parameter keys available are:

* [label](#param-label)
* [tooltip](#param-tooltip)
* [type](#param-type)
* [option](#param-option)
* [default](#param-default)

The image below illustrates the parameters key.

![Field configuration parameters](/images/developers/05_custom_fields/field_configuration_1.png)

<a name="param-label"></a>
### Label

This is the label of configuration parameter. This can be a language string and it will be automatically translated when the configuration is loaded.

<a name="param-tooltip"></a>
### Tooltip

This is the tooltip of the configuration parameter. This can be a language string and it will be automatically translated when the configuration is loaded.

<a name="param-type"></a>
### Type

This defines the type of the configuration parameter. The available types are:

* boolean \*
* text/input
* textarea
* select/dropdown/list \*\*
* checkbox \*\*
* choices \*\*\*

\* Defaults to boolean if it is not defined.

\*\* Parameter [option](#param-option) is required for these types.

\*\*\* Parameter [option](#param-option) is optional and is used to define default choices.

<a name="param-option"></a>
### Option

This defines the option available corresponding to the type of the parameter. This parameter will only apply if the type of the parameter is one of the following:

* select/dropdown/list
* checkbox
* choices

Format of the option is basically an array of objects.

	{
		"options": {
			"label"		: "Available options",
			"tooltip"	: "Select the options available to user",
			"type"		: "checkbox",
			"option": [
				{
					"label"		: "Option 1",
					"value"		: 1,
					"default"	: true
				},
				{
					"label"	: "Option 2",
					"value"	: 2
				}
			]
		}
	}

_Note: Key `default` is false by default and is only applied to `checkbox` and `choices`. This determines if the `checkbox` or `choices` should be pre-checked / pre-selected or not._

<a name="param-default"></a>
### Default

This defines the default value of the parameter when the configuration is loaded and there are no pre-saved value. This is optional.

<a name="override-parameters"></a>
## Override parameters

__Important! This is an advance feature and might caused unwanted result.__

Some of the default parameters might not make sense in your custom fields. This gives you the ability to [change the default parameter](#change-parameter), eg: label, tooltip, default, type, or even [hide the paramater](#hide-parameter) from being shown/loaded.

<a name="change-parameter"></a>
### Changing a parameter

By default, when you add a field into the profile, the title of the default is always loaded as "Set a title".

![Title parameter's default value](/images/developers/05_custom_fields/field_configuration_2.png)

You can change this default value by redefining the parameter:

	{
		"title": {
			"default": "This is a different default title"
		}
	}

When redefining a parameter, you do not need to redeclare the other keys, you only need to declare the keys of the parameter that you would like to change. In this example, we only change the default value of the title, but not the label, tooltip and type of the title configuration parameter.

<a name="hide-parameter"></a>
### Hiding a parameter

If you would like to hide a parameter, for example, your field does not requires a `title` configuration parameter, just redefine the same key and pass in the value `false`.

	{
		"title": false	
	}

## Calling field configuration parameter

The field configuration parameter is already initialized in your class in the property `$params`. Refer to [available properties section of Triggers](triggers#availableproperties) for more information.

`$params` is in the form of SocialRegistry/JRegistry. You can then get the value of a parameter with the `get` method of the registry and passing in the `name` of the configuration parameter.

	$minimumChar = $this->params->get('minimum_character');