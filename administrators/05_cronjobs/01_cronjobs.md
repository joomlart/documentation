If `Cronjobs` sounds foreign to you, no fret. It's actually just a task scheduler on most linux / unix environment. Most, if not all Linux / UNIX hosting accounts comes with a cronjob service included. If your hosting provider does not provide a cronjob interface, it's best to start looking for another host.

## Why do we need cronjobs?
Because processing emails are always slow. When there are hundreds of emails to be processed at a time, the server needs to contact the respective mail servers to deliver the mail. However, the process for each delivery might differ from time to time and this would result in higher bounce rate of users on your site.

Consider this scenario:
>John posted a comment on an update which has 10,000 previous comments. To deliver 10,000 emails as soon as you post a comment would take more than an hour. Would you want your user's to wait?

## What if my host doesn't have cronjobs?
If your web host doesn't support cron jobs, it's time that you ditch them or get them to allow cron jobs. It's one of the most important tools to build a site. If your current web host doesn't support cron jobs, you could also opt for other cronjob services such as:

* http://setcronjob.com
* http://cronjob.com

Altneratively, if this it is viable to switch your hosting provider, these are the list of web hosting companies that we would strongly suggest:

* [CloudAccess](http://cloudaccess.net)
* [Siteground](http://sitegoround.com)
* [Hostgator](http://hostgator.com)