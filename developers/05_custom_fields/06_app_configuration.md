_This is optional and only needed if the field have extra per-application-configuration_

Not to be confused with [field configuration](field_configuration), this configuration applies accross all field, while field configuration is settings for admin to apply on per-field basis.

This is useful for cases such as reCaptcha public key and private key settings, where it is applied accross all field instances that the admin will add into the profile.

## Application configuration parameters

Create an admin.json file in the config folder from the root of the field:

`/config/admin.json`

The configuration parameters should be defined in JSON format. The structure of the JSON is an array of objects that defines the sections in the application settings page.

	[
		// Defines a section in the application settings page
		{
			"title"		: "reCaptcha configuration",
			"fields"	:
		
			// Defines the configuration parameter in this section
			[
				{
					"label"		: "Public key",
					"tooltip"	: "Enter your reCaptcha public key",
					"name"		: "publickey",
					"type"		: "text"
				},
				{
					"label"		: "Private key",
					"tooltip"	: "Enter your reCaptcha private key",
					"name"		: "privatekey",
					"type"		: "text"
				},
				{
					"label"		: "Use SSL",
					"tooltip"	: "Determines if reCaptcha should be loaded with SSL",
					"name"		: "ssl",
					"type"		: "boolean",
					"default"	: true
				}
			]
		}
	]

Parameter keys available for Section are:

* title - defines the title of the section
* fields - defines the fields in this section

Parameter keys available for Fields are:

* label - the label of this configuration parameter
* tooltip - the tooltip of this configuration parameter
* type - the type of this configuration parameter
* default - the default value of this configuration parameter

Note: Parameters key for Fields are similar to [parameter keys for field configuration](field_configuration#extra-parameters).

## Calling application configuration parameter

You can get the application configuration parameter in SocialRegistry/JRegistry format by calling:

	$params = $this->field->getApp()->getParams();

You can then get the value of the paramater with the `get` method of the registry and passing in the `name` of the configuration parameter.

	$publickey = $params->get('publickey');