This guide would guide you through the process of setting up cronjobs using cPanel. If your hosting provider provides you with cPanel, this guide is for you.

## Accessing cPanel
To access the cronjobs section, you would just need to click on the cronjob icon highlighted below:

![Cronjob Button](/images/administrators/cronjobs/cpanel/cronjob_button.jpg "Cronjob Button")

## Getting Notified
This is usefull and you should set this up so that you know the cronjob is executing correctly. To setup email notifications for the cronjob process, enter your e-mail adddress as shown in the figure below:

![Cronjob Notifications](/images/administrators/cronjobs/cpanel/notifications.jpg "Cronjob Notifications")

To specify an email address:

1. Enter your e-mail address as shown in the screen above.
2. Click on the `Update Email` button as shown in the screen above.

## Creating the Cronjob
Once the notification have been setup, you will want to now create the cronjob. To setup cronjob, follow the steps below:

![Cronjob Interval](/images/administrators/cronjobs/cpanel/interval.jpg "Cronjob Interval")

Choose ther interval for the cronjob to get executed.

* `Common Settings` - This allows you to select a commonly used interval. (**Recommended Every 5 Minutes**)
* `Minute` - This sets the cronjob to execute at every **x minutes**.
* `Hour` - This sets the cronjob to execute at every **x hour**.
* `Day` - This sets the cronjob to execute at every **x day**.
* `Month` - This sets the cronjob to execute at every **x day**.
* `weekday` - This sets the cronjob to execute at **selected weekdays**.

In the command field, this is where you tell cPanel the command that you wish to execute.

Example [^1]:

```bash
/bin/wget -O /dev/null "http://site.com/index.php?option=com_easysocial&cron=true"
```

Once you are done, click on the `Add New Cron Job` button as shown on the screen above and you are good to go.

[^1]: Not every hosting provider supports `/bin/wget`. It's best that you contact your hosting provider to find out the utility that can be used to access websites.