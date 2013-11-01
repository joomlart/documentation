Before we begin with the installation over directory, please ensure that you have already downloaded the following packages from our site:

* `Launcher Package`
* `Component Package`
 
If you have not downloaded it yet, please refer to the [guide here](/administrators/setup/downloading).

## Install Launcher Package first
The component package still relies on the launcher. You will need to install the launcher package first.

Proceed to the Joomla! extensions manager.

![Joomla Extensions Manager](/images/administrators/02_setup/install_directory_1.png)




Click on the `browse button` and select the launcher file that you have already downloaded.

![Joomla Extensions Manager Browse Files](/images/administrators/02_setup/install_directory_2.png)




Once you have selected the file, click on the `Upload & Install` button.

![Joomla Extensions Manager Upload & Install](/images/administrators/02_setup/install_directory_3.png)




Click on the `Proceed with Installation` button to proceed with the component installation.

![Joomla Extensions Manager Upload EasySocial Successfull](/images/administrators/02_setup/install_directory_4.png)




You will then be presented with a screen that looks similar to below:

![EasySocial Requirements](/images/administrators/02_setup/install_directory_5.png)

<div class="alert alert-notice">If you encounter an error on this page, please proceed with the troubleshooting guide for system requirements</div>




If everything is well, click on the `Next Step` button and you will be presented with the screen below which will diagnose the folders on your site. All the folders listed here needs to be writable. Otherwise the system would not allow you to proceed with the installation. 

![EasySocial Folder Writable](/images/administrators/02_setup/install_directory_6.png)

<div class="alert alert-notice">If you encounter an error on this page, please proceed with the troubleshooting guide for folder permissions</div>



If all the folders are writable, it's awesome! Click on the `Next Step` button to proceed with the next step and you will be presented with a screen that allows you to choose between a `Network Installation` or `Directory Installation`. Since you have downloaded the `Component Package`, we will now choose the `Installation over Directory` method.

![EasySocial Install Over Directory](/images/administrators/02_setup/install_directory_7.png)

Then, proceed to the next section to `Upload Component Package`.

<br />
## Upload Component Package
Once the launcher installation is completed, you will then need to upload the component package to the following path:

`/administrator/components/com_easysocial/setup/packages`


Once the file is already uploaded, you should be able to select the package that you have uploaded and you will see a screen which looks similar to the screen below.

![EasySocial Select Package](/images/administrators/02_setup/install_directory_8.png)

Select the package that you have uploaded and hit the `Next Step` button and proceed to the `Finalizing Installation` section next.

<br />



## Finalizing Installation
Once you have completed the steps earlier, you will then see the installation screen that looks similar to the screen below. The installer is copying the files and performing necessary database table creations on the site.

![EasySocial Select Package](/images/administrators/02_setup/install_directory_9.png)


When the progress is completed, click on the `Next Step` button and you will be presented with a screen below. The system is running some integrity checks and also ensuring that all the database tables are up to date as well.

![EasySocial Maintenance](/images/administrators/02_setup/install_directory_10.png)


Once the maintenance progress is completed, hit the `Next Step` button. You have now completed the installation of EasySocial and you can start using EasySocial on your site.

