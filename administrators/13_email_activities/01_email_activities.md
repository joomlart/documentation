EasySocial utilizes a mail delivery pool which ensures that the page would not time out when e-mails are being dispatched. E-mail activities will display e-mails that are queued and sent in the e-mail delivery system.

![E-mail Activities in EasySocial](/images/administrators/13_email_activities/email_activity_1.png)

You may also preview the e-mail by clicking on the title. You should see a screen with the preview of the e-mail as below.

![E-mail Preview in EasySocial](/images/administrators/13_email_activities/email_activity_2.png)

### Table Definition
`Title` - This is the subject of the email.
`Recipient` - This is the recipient of the e-mail.
`Priority` - This is the priority that is set for the e-mail.
`State` - The state of the e-mail whether it has been delivered, pending or if it has errors.
`Created` - The creation date of the e-mail in the delivery pool.
`ID` - The unique id for the mail pool item.

### Actions on page
`Mark Sent` - Mark e-mails as sent so that it would not be sent again when mail delivery occurs.
`Mark As Pending` - Mark e-mails as pending so that it would be delivered again when mail delivery occurs.
`Purge Sent` - This will purge all sent e-mails from the mail pool.
`Purge Pending` - This will purge all pending e-mails from the mail pool.
`Purge All` - This will purge all e-mails from the mail pool.