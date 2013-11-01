Just like applications, you as a template provider or template club can create template packages which you can then ship to the end user. By creating your own template package, you will be able to create additional configurations that is used only within your own template.


## Structure
```markup
Main Folder
|
|- - - styles (Keep your .less files here)
|
|- - - config (This is where EasySocial will look for template configuration)
```

### Config folder
The config folder contains rich meta data about your template. All the files that are located within this folder should be in `json` format. 

There are 3 main files that EasySocial searches through this folder:

* defaults.json (This is where all the default settings are kept)
* form.json (This is where you define your own form settings)
* template.json (This is where you specify your template details. Similar to templateDetails.xml)


##### template.json

```markup
{
	"name"		: "Wireframe",
	"element"	: "wireframe",
	"desc"		: "This is the base theme for EasySocial and other themes will inherit from this base theme. Any customizations should be done on this base theme.",
	"author"	: "Stack Ideas Sdn Bhd",
	"email"		: "support@stackideas.com",
	"website"	: "http://stackideas.com",
	"created"	: "26th May 2013",
	"version"	: "1.0.1",
	"servers"	: 
	{
		"update"	: "http://stackideas.com/",
		"version"	: "http://stackideas.com"
	}
}
```

##### form.json

```markup
[
	{
		"title"		: "Registration",
		"fields"	:
		[
			{
				"label"		: "Show headers in selecting profile page",
				"name"		: "registration_profile_headers",
				"tooltip"	: "Determines if the heading that appears below the toolbar should be enabled.",
				"type"		: "boolean",
				"default"	: true
			},
			{
				"label"		: "Show Profile Avatar",
				"name"		: "registration_profile_avatar",
				"tooltip"	: "Determines if the profile avatar should be visible or not.",
				"type"		: "boolean",
				"default"	: true
			},
			{
				"label"		: "Show Profile Description",
				"name"		: "registration_profile_desc",
				"tooltip"	: "Determines if the profile description should be visible or not.",
				"type"		: "boolean",
				"default"	: true
			},
			{
				"label"		: "Show Profile Registration Type",
				"name"		: "registration_profile_type",
				"tooltip"	: "Determines if the profile description should be visible or not.",
				"type"		: "boolean",
				"default"	: true
			},
			{
				"label"		: "Show Users Registered in Profile",
				"name"		: "registration_profile_users",
				"tooltip"	: "Determines if users that are registered in that profile should be visible or not.",
				"type"		: "boolean",
				"default"	: true
			},
			{
				"label"		: "Show progress bar during registration",
				"name"		: "registration_progress",
				"tooltip"	: "Determines if users should be able to see the registration progress bar.",
				"type"		: "boolean",
				"default"	: true
			},
			{
				"label"		: "Show selected profile during registration",
				"name"		: "registration_profile_selected",
				"tooltip"	: "If this option is enabled, users would be able to see the profile that they have selected initially.",
				"type"		: "boolean",
				"default"	: true
			}
		]
	},
	{
		"title"		: "Toolbar",
		"fields"	:
		[
			{
				"label"		: "Show Toolbar",
				"name"		: "toolbar",
				"tooltip"	: "Determines if the toolbar should be enabled.",
				"type"		: "boolean",
				"default"	: "true"
			},
			{
				"label"		: "Show Dashboard",
				"name"		: "toolbar_dashboard",
				"tooltip"	: "Determines if the home icon should be visible or not.",
				"type"		: "boolean",
				"default"	: "true"
			},
			{
				"label"		: "Show Search",
				"name"		: "toolbar_search",
				"tooltip"	: "Determines if the search box should be enabled or not.",
				"type"		: "boolean",
				"default"	: "true"
			},
			{
				"label"		: "Show Login",
				"name"		: "toolbar_login",
				"tooltip"	: "Determines if the login icon should be visible or not.",
				"type"		: "boolean",
				"default"	: "true"
			},
			{
				"label"		: "Show Account dropdown",
				"name"		: "toolbar_account",
				"tooltip"	: "Determines if the Your Profile submenu item should be visible or not.",
				"type"		: "boolean",
				"default"	: "true"
			}

		]
	},
	{
		"title"		: "Stream",
		"fields"	:
		[
			{
				"label"		: "Date display style",
				"name"		: "stream_datestyle",
				"tooltip"	: "Determines the date display style in frontend",
				"type"		: "select",
				"options"	:
				[
					{
						"title"	: "Time elapsed style",
						"value" : "elapsed"
					},
					{
						"title"	: "Normal datetime style",
						"value" : "datetime"
					}
				],
				"default"	: "elapsed"
			},
			{
				"label"		: "Datetime format",
				"name"		: "stream_dateformat_format",
				"tooltip"	: "Determines the format of datetime when normal datetime style selected.",
				"type"		: "text",
				"default"	: "Y-m-d H:i"
			}
		]
	},
	{
		"title"		: "Profile",
		"fields"	:
		[
			{
				"label"		: "Display Profile Cover",
				"name"		: "profile_cover",
				"tooltip"	: "If enabled, user's profile cover will be displayed in their profile.",
				"type"		: "boolean",
				"default"	: true
			},
			{
				"label"		: "Display Points",
				"name"		: "profile_points",
				"tooltip"	: "If enabled, user's points will be displayed in their profile.",
				"type"		: "boolean",
				"default"	: true
			},
			{
				"label"		: "Display Badges",
				"name"		: "profile_badges",
				"tooltip"	: "If enabled, user's badges will be displayed in their profile.",
				"type"		: "boolean",
				"default"	: true
			},
			{
				"label"		: "Display Age",
				"name"		: "profile_age",
				"tooltip"	: "If enabled, user's age will be displayed in their profile.",
				"type"		: "boolean",
				"default"	: true
			},
			{
				"label"		: "Display Gender",
				"name"		: "profile_gender",
				"tooltip"	: "If enabled, user's gender will be displayed in their profile.",
				"type"		: "boolean",
				"default"	: true
			},
			{
				"label"		: "Display Address",
				"name"		: "profile_address",
				"tooltip"	: "If enabled, user's address will be displayed in their profile.",
				"type"		: "boolean",
				"default"	: true
			},
			{
				"label"		: "Display Website",
				"name"		: "profile_website",
				"tooltip"	: "If enabled, user's website will be displayed in their profile.",
				"type"		: "boolean",
				"default"	: true
			},
			{
				"label"		: "Display Report User",
				"name"		: "profile_report",
				"tooltip"	: "If enabled, report link will be displayed in the user's profile.",
				"type"		: "boolean",
				"default"	: true
			}
		]
	},
	{
		"title"		: "Apps",
		"fields"	:
		[
			{
				"label"		: "Display sorting items",
				"tooltip"	: "If enabled, user can sort apps when they are viewing the apps.",
				"name"		: "apps_sorting",
				"type"		: "boolean",
				"default"	: true
			}
		]
	},
	{
		"title"		: "Users",
		"fields"	:
		[
			{
				"label"		: "Users Per Page",
				"tooltip"	: "Specify the number of users to display per page in the users listings",
				"name"		: "userslimit",
				"type"		: "pagination",
				"start"		: "5",
				"increment"	: "5",
				"max"		: "100",
				"default"	: "10"				
			}
		]
	},
	{
		"title"		: "Badges",
		"fields"	:
		[
			{
				"label"		: "Badges Per Page",
				"tooltip"	: "Specify the number of badges to display per page in the badge listings",
				"name"		: "badgeslimit",
				"type"		: "pagination",
				"start"		: "5",
				"increment"	: "5",
				"max"		: "100",
				"default"	: "10"
			}
		]
	},
	{
		"title"		: "Points",
		"fields"	:
		[
			{
				"label"		: "Points Per Page",
				"tooltip"	: "Specify the number of points to display per page in the points listings",
				"name"		: "pointslimit",
				"type"		: "pagination",
				"start"		: "5",
				"increment"	: "5",
				"max"		: "100",
				"default"	: "10"
			}
		]
	}
]
```

#### defaults.json
This is where all default settings should be kept.

```markup
{
	"profile_cover"		: true,
	"toolbar" 			: true,
	"toolbar_dashboard"	: true,
	"toolbar_login"		: true,
	"toolbar_search" 	: true,
	"toolbar_account" 	: true,
	"badgeslimit"		: 10,
	"userslimit"		: 10,
	"pointslimit"		: 10
}
```