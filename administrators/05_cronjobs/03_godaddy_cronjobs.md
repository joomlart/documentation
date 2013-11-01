This guide would guide you through the process of setting up cronjobs if you are hosted on Godaddy.


## Accessing Godaddy Control Panel
Head on to [GoDaddy.com](http://www.godaddy.com/) and Login, then go to your Products tab and click on the "Launch" button.

![Godaddy Control Panel](/images/administrators/cronjobs/godaddy/cpanel.jpg "Godaddy Control Panel")

Once you are logged in, click on the `Cron Job Manager` button as shown in the screen below:

![Godaddy Cronjob Manager](/images/administrators/cronjobs/godaddy/manager.jpg "Godaddy Cronjob Manager")

## Preparing the cron.php File
Before creating the cronjob on Godaddy, you will first need to edit the file `/components/com_easysocial/cron.php`. Load this file up with your favorite editor and you should see some codes that resembles the screen below:

![Cronjob File](/images/administrators/cronjobs/godaddy/file.png "Cronjob File")

You will need to rename 'site.com' to your own domain name. Remember, you **`DO NOT`** need to add the `http://` or `https://` prefixes.


## Creating the Cronjob
Once you on the cronjob page, click on the `Create` button to create a new cronjob. Now, click on the `Browse` button and then navigate to `/components/com_easysocial/cronjob.php` to select the `cron.php` file [^1].

![Godaddy Cronjob Browser](/images/administrators/cronjobs/godaddy/browser.jpg "Godaddy Cronjob Browser")

![Godaddy Cronjob](/images/administrators/cronjobs/godaddy/cronjob.jpg "Godaddy Cronjob")

After selecting the `cron.php` file, you will then need to set the settings below:

* `Frequency` - Recommended to be set **Hourly**
* `Minute` - Recommmended to be set **x:00**


[^1]: Godaddy does not support `wget` or `lynx` on their cronjob. You could only utilize PHP scripts on their cronjob.