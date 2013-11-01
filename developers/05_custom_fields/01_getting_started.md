EasySocial also comes with an extended custom fields system that allows you to create custom field applications. Custom field applications enhances the capability of the existing custom field system.

_A custom field is a subset of an EasySocial application, but the structure and logic is built differently to cater to custom field's specific needs that does not necessarily make sense in an application._

## Custom Field Structure
Custom Field applications are stored in the following location by default:

`/media/com_easysocial/apps/fields/user/<element>/`

An application structure should have a basic structure of the following:

`textbox/`  
|  
|_ _ _ `textbox.xml` ([Application Manifest file](manifest_file))  
|_ _ _ `textbox.php` ([Main application file](triggers))  
|_ _ _ `config/`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|_ _ _ `config.json` ([Field configuration file](field_configuration))  
|_ _ _ `themes/`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|_ _ _ `default/`  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|_ _ _ `content.php` ([Main theme file](field_output))  

<a href="/files/developers/field_sample.zip" class="btn btn-success""><i class="icon-download"></i> &nbsp; Download Sample Field</a>   <a href="/developers/applications/manifest_file" class="btn btn-primary"">Start Documentation &rarr;</a>

## Documentation contents

1. [Getting started](getting_started)
2. [Application Manifest file](manifest_file)
3. [Triggers & application file](triggers)
4. [Field configuration file](field_configuration)
5. [Field themes and output](field_output)

## Extended/Advance features documentation

1. [Application configuration file](app_configuration)
2. [Field model, table, view, helper, ajax](helpers)
3. [Widgets](widgets)