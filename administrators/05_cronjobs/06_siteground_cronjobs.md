## Introduction
<p>Cron jobs are scheduled tasks that runs at intervals or predefined times on the server. </p>
<p>
The purpose of cron job is to execute series of simple tasks from a script file
and cPanel offers the user interface as a tool to ease end users for setting up cron jobs.
</p>

## Accessing your cpanel
<img src="/images/administrators/04_configuration/07_setting_up_cronjob_with_siteground/cronjob_button.JPG" style="width: 600px">


## Setup Email
<img src="/images/administrators/04_configuration/07_setting_up_cronjob_with_siteground/email.JPG"  style="width: 600px">
<p>Specify an email address at the cron email section to receive notifications or status message whenever your cron jobs are executed.</p>
<p>To specify an email address:</p>

<p>Step 1. Enter the email address at which you wish to receive the notifications in the email field.</p>

<p>Step 2. Click the Update Email button.</p>

## Adding a cron job

<p>To set up a cron job:</p>

**Step 1. Configure the interval at which you wish to run the cron job.**

<img src="/images/administrators/04_configuration/07_setting_up_cronjob_with_siteground/interval.JPG"  style="width: 600px">

- Minute — Use this menu to select the number of minutes between running the cron job, or the minute each hour on which you wish to run the cron job.
- Hour — Use this menu to select the number of hours between running the cron job, or the hour each day on which you wish to run the cron job.
- Day — Use this menu to select the number of days between running the cron job, or the day of the month on which you wish to run the cron job.
- Month — Use this menu to select the number of months between running the cron job, or the month of the year in which you wish to run the cron job.
- Weekday — Use this menu to select the day(s) of the week on which you wish to run the cron job.


**Step 2. In the Command to run field, type the command you wish the system to run.**
<p>Example:</p>
> /bin/wget -O /dev/null "http://stackideas.com/index.php?option=com_easydiscuss&task=cron"

<p>
You can have cron send an email everytime it runs a command.
If you do not want an email to be sent for an individual cron job you can redirect the command's output to:
</p>
> /dev/null like this: mycommand >/dev/null 2>&1

**Step 3. Click Save Crontab button.**

<p>This concludes how to create a cron job in cPanel.</p>
<img src="/images/administrators/04_configuration/07_setting_up_cronjob_with_siteground/cron_task.JPG"  style="width: 600px">
