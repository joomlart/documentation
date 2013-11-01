The manifest file in any EasySocial application should always be an XML file. Please remember that the XML must be stored in UTF-8 encodings otherwise the manifest file would not be readable.


### Sample
You may find a sample of the manifest file below:

```php
<?xml version="1.0" encoding="utf-8"?>
<social type="apps" group="user">
	<!-- 
		This should be the name of your app that will appear in the application listings.
	-->
	<name>Textbook</name>

	<!--
		This is the unique element of your app. It must be lowercased.
	-->
	<element>textbook</element>

	<!--
		Give an identifier for your self.
	-->
	<author>%AUTHOR%</author>

	<!--
		Let the user's know how they could easily reach you.
	-->
	<url>%WEBSITE%</url>

	<!--
		The creation date of this app.
	-->
	<created>%DATE_CREATED%</created>

	<!--
		Give a version for your app. Ideal to follow the semantic version guideline, http://semver.org/
	-->
	<version>1.0.1</version>

	<!--
		Any copyright message for your app
	-->
	<copyright>Copyright (C) 2010 - 2013 %COMPANY%</copyright>

	<!--
		The license for your app
	-->
	<license>http://www.gnu.org/licenses/gpl-2.0.html GNU/GPL</license>

	<!--
		Give a description for your app. The app's language file will be loaded during installation, so your text could also
		be in a form of a language string
	-->
	<description><![CDATA[APP_TEXTBOOK_DESCRIPTION]]></description>


	<!--
		If this option is enabled, this application behavior allows user to install the app.
	-->
	<installable>true</installable>

	<!--
		When an app is made as core, site administrator will not be able to delete the app.
	-->
	<core>false</core>

	<!--
		Define view types available for the app on this section.

		Views:
		1. Dashboard - The current logged in user's dashboard
		2. Profile - The user's profile page.

		View Types:
		1. Canvas - This allows your app to be displayed on a page of it's own.
		2. Embed - This will load your app via AJAX and contents will be displayed on the respective views.
	-->
	<views>
		<view type="canvas">dashboard</view>
		<view type="canvas">profile</view>
	</views>

	<!--
		Your app could also behave like a widget if the following option is enabled. Widgets are pretty identical like modules but 
		it allows users on the site to install them as apps.
	-->
	<widget>true</widget>

	<!--
		This is pretty similar to how Joomla looks for files.
	-->
	<files>

		<!--
			This determines that the app contains folders
		-->
		<folder>assets</folder>
		<folder>controllers</folder>
		<folder>models</folder>
		<folder>tables</folder>
		<folder>themes</folder>
		<folder>views</folder>

		<!--
			This determines that the app contains files
		-->
		<file>textbook.php</file>
		<file>textbook.xml</file>

		<!--
			With the sql tag, you will be able to execute SQL queries during the installation of the application.
		-->
		<sql>install.sql</sql>
	</files>

	<!--
		You may define language files that the app installs on the site. 
		This file needs to be at the root directory of your app and it will be copied to the respective locale folder.

		Example: type="en-GB" would lead to the file being copied to /language/en-GB/
	-->
	<languages>
		<language type="en-GB">en-GB.plg_app_user_textbook.ini</language>
	</languages>

</social>
```

## Elements
The manifest files are divided into the following sections

* name
* element
* author
* url
* created
* version
* copyright
* description
* license
* installable
* core
* widget
* system
* views
* files
* languages
* updates


### Name
This is the name of your application. This should contain a very simple and meaningfull title.

```php
	
	<!-- 
		This should be the name of your app that will appear in the application listings.
	-->
	<name>Textbook</name>
```

### Created
This determines the creation or last updated date of your application.

```markup

	<!--
		The creation date of this app.
	-->
	<created>%DATE_CREATED%</created>

```

### Version
This determines the current version of the app that is installed. It is ideal to use [Semantic Versioning](http://semver.org/spec/v2.0.0.html)

```php

	<version>1.0.1</version>
```

### Copyright
Your own copyright message should display here.

```php

	<copyright>Copyright (C) 2010 - 2013 Stack Ideas Sdn Bhd</copyright>
```

### License
All applications that are derived from EasySocial must be derived from the [GNU GPL license](http://www.gnu.org/licenses/gpl-2.0.html GNU/GPL)

```php
	<license>http://www.gnu.org/licenses/gpl-2.0.html GNU/GPL</license>
```

### Description
The description will be visible to the site owner / admin when they install the application on the site. It should be wrapped within a proper CDATA tag to avoid invalid XML markup.

```markup
	<description><[CDATA[APP_BLOG_APP_DESC]]></description>
```

### Core
This determines if the application should be a core application or not. Core application cannot be uninstalled from the site once it is installed.

```php

	<!--
		When an app is made as core, site administrator will not be able to delete the app.
	-->
	<core>false</core>
```

### Installable
The installable tag determines if the app is installable by the user. If the app is installable, the user will be allowed to install the application when viewing the applications area.* 

```php

	<!--
		If this option is enabled, this application behavior allows user to install the app.
	-->
	<installable>true</installable>
```

### Widget
The widget tag determines if the app provides a widget service to the user. Widgets will only be loaded provided that the application register themselves using the following element.

```php

	<!--
		Your app could also behave like a widget if the following option is enabled. Widgets are pretty identical like modules but 
		it allows users on the site to install them as apps.
	-->
	<widget>true</widget>
```

### System
This is not often used because when this element exists in your manifest file, it tells the system that your app doesn't display any data on the page. It simply is an application service that processes application triggers.

```markup
<system>true</system>
```

### Views
Application views defines the available views that your app has. You can learn more about <a href="/developers/applications/views">Application Views here</a>.

```php

	<!--
		Define view types available for the app on this section.

		Views:
		1. Dashboard - The current logged in user's dashboard
		2. Profile - The user's profile page.

		View Types:
		1. Canvas - This allows your app to be displayed on a page of it's own.
		2. Embed - This will load your app via AJAX and contents will be displayed on the respective views.
	-->
	<views>
		<view type="canvas">dashboard</view>
		<view type="canvas">profile</view>
	</views>
```







