If you have not created an Amazon account, be sure to register for an account at [Amazon](http://amazon.com/s3/). Once you have your account created, you will need to login to [Amazon Console](http://aws.amazon.com/console/).


## Obtaining Access Keys
You will first need to generate your access id and secret key through the Amazon Console. Once logged in, hover over your name on the top right corner and click on `Security Credentials`

![Security Credentials](/images/administrators/18_remote_storage/aws_security_credentials.png)

Then, click on the `Create New Access Key` as shown in the screen below:

![Create New Access Key](/images/administrators/18_remote_storage/aws_create_access.png)

Upon creation, you need to click on the `Show Access Key` as you will need to copy both the `Access Key ID` and `Secret Access Key` to a safe location:

![Copy Access Key](/images/administrators/18_remote_storage/aws_show_access_key.png)

Upon obtaining both the `Access Key Id` and `Secret Access Key`, proceed to the next section to set them up in EasySocial.


## Setting Access Keys
Copy the `Access Key Id` and `Secret Access Key` that you have received into the remote storage settings as shown in the screen below:

![Set Access Key](/images/administrators/18_remote_storage/aws_easysocial_settings.png)

Then, click on the `General` tab and ensure that all of the storage are set to `Amazon S3` or you could pick and match services that you would like to use on Amazon S3 or local storage.

![Set Access Key](/images/administrators/18_remote_storage/aws_easysocial_storage_settings.png)

Once you are done, save the settings and you are good to go. Next, you will need to [create the cronjob](/administrators/cronjobs/cronjobs) so that the system will be able to upload the files over silently.