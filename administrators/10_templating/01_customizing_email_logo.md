By default, the email template would include a logo automatically. If you would like to customize or change the logo that appears in the e-mail template, you could create a template override folder and store the image of the logo.

Ideally, the size of the logo should be within `160px` width x `40px` height to avoid distorting the layout.

## Default Logo
The default logo is included in the `wireframe` theme and it can be accessed at the path below:

`/components/com_easysocial/themes/wireframe/images/emails/logo.png`

Sample of logo:

![Default Email Logo](/images/administrators/configuration/email_logo.png "Default Email Logo")


## Overriding the logo
To create a template override, you should go to your template's folder. Assuming that you are using `protostar` template for Joomla, you could create the folder below:

`/templates/protostar/html/com_easysocial/emails/`

Then, upload the logo.png file into this folder and EasySocial will automatically pick this up.