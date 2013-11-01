The manifest file in EasySocial field is in XML format. Make sure that the XML is stored in UTF-8 encoding.

## Sample

Below is a sample of a manifest file:

	<?xml version="1.0" encoding="utf-8"?>
	<social type="fields" group="user">

		<!-- Name of the field that will appear in the application/field listing -->
		<name>Textbox</name>
	
		<!-- This is the unique element of your app. It must be lowercased -->
		<element>textbox</element>
	
		<!-- Your/author's name/identifier -->
		<author>%AUTHOR%</author>

		<!-- Your/author's website -->
		<url>%WEBSITE%</url>

		<!-- The creation date of this field -->
		<created>%DATE_CREATED%</created>

		<!-- Field version. Ideal to follow the semantic version guideline, http://semver.org/ -->
		<version>1.0.0</version>

		<!-- Copyright message of this field -->
		<copyright>Copyright (C) 2010 - 2013 %COMPANY%</copyright>

		<!-- The license of this field -->
		<license>http://www.gnu.org/licenses/gpl-2.0.html GNU/GPL</license>

		<!-- Give a description for this field. This can be in a form of a language string -->
		<description><![CDATA[PLG_FIELDS_TEXTBOX_DESCRIPTION]]></description>
	
		<!-- Determine if this is a mandatory field, defaults to false -->
		<core>false</core>
	
		<!-- Determine if this is a unique field, defaults to false -->
		<unique>false</unique>
	
		<!-- This is similar to how Joomla looks for files. -->
		<files>

			<!-- Defines the folders that the field contains -->
			<folder>config></folder>
			<folder>themes</folder>

			<!-- Defines the files that the field contains -->
			<file>textbox.php</file>
			<file>textbox.xml</file>

			<!-- SQL queries will be executed during installation -->
			<sql>install.sql</sql>
		</files>
	
		<!--
			Defines language files of the files.
			This file needs to be at the root directory of your field and it will be copied to the respective locale folder.
		-->
		<languages>
			<language type="en-GB">en-GB.plg_fields_user_textbox.ini</language>
		</languages>
	</social>

## Elements

The manifest files are divided into the following elements

* [name](#manifest-name)
* [element](#manifest-element)
* [author](#manifest-author)
* [url](#manifest-url)
* [created](#manifest-created)
* [version](#manifest-version)
* [copyright](#manifest-copyright)
* [license](#manifest-license)
* [description](#manifest-description)
* [core](#manifest-core)
* [unique](#manifest-unique)
* [files](#manifest-files)
* [languages](#manifest-langauges)

<a name="manifest-name"></a>
## Name

This is the name and the title of the field. This title will appear in the application and field listing.

	<name>Textbox</name>

<a name="manifest-element"></a>
## Element

This is the element name of the field. This has to be all lowercase and unique.

	<element>textbox</element>

<a name="manifest-author"></a>
## Author

This is your/author's name or identity.

	<author>John Doe</author>

<a name="manifest-url"></a>
## Url

This is your/author's reference url/address/website.

	<url>http://yoursite.com</url>

<a name="manifest-created"></a>
## Created

This is the creation date or the last updated date of the field.

	<created>1/1/2013</created>

<a name="manifest-version"></a>
## Version

This is the current version number of the field. It is ideal to follow the format of [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

	<version>1.0.0</version>

<a name="manifest-copyright"></a>
## Copyright

This is the copyright message of the field.

	<copyright>Copyright (C) 2010 - 2013 Your Company's Name</copyright>

<a name="manifest-license"></a>
## License

All applications that are derived from EasySocial must be derived from the [GNU GPL license](http://www.gnu.org/licenses/gpl-2.0.html GNU/GPL)

	<license>http://www.gnu.org/licenses/gpl-2.0.html GNU/GPL</license>

<a name="manifest-description"></a>
## Description

The description will be visible to the site owner / admin when they install the field on the site. It should be wrapped within a proper CDATA tag to avoid invalid XML markup.

	<description><[CDATA[PLG_FIELDS_TEXTBOX_DESC]]></description>
	
<a name="manifest-core"></a>
## Core

This determines if the field is a core field or not. If set to true, it means that the field is a mandatory field and must be added into the profile. This is false by default and developers are suggested to leave this as false.

	<core>false</core>

<a name="manifest-unique"></a>
## Unique

This determines if the field is a unique field or not. If set to true, it means that the field is a unique, and can only be added once into the profile. This is false by default and if only need to be set to true if the field is not a general purpose field.

	<unique>false</unique>

<a name="manifest-files"></a>
## Files

This declares the folders and files of the fields and this is similar to how Joomla's manifest file defines the folders and files.

	<files>
		<folder>config</folder>
		<folder>themes</folder>

		<file>textbox.php></file>
		<file>textbox.xml></file>
	</files>

<a name="manifest-languages"></a>
## Languages

This declares the language file to install along with the field and this is also similar to how Joomla's manifest file defines the language files.

The file needs to be at the root directory of the field app.

	<languages>
		<language type="en-GB">en-GB.plg_fields_user_textbox.ini</language>
	</languages>