With the extensive amount of libraries in `EasySocial`, you can start building apps for your extension or external scripts easily. Applications in EasySocial can be created for multiple purposes. These are some of the purposes of building applications around EasySocial.

* Control the behavior of certain actions via triggers.
* Display widgets on a user's profile or dashboard.
* Display application output on a user's profile or dashbord.

EasySocial has already catered most if not all of your application needs. You can start exploring the following ways to start building your awesome apps.

## Application structure
Applications are stored in the following location by default:

`/media/com_easysocial/apps/user/<element>/`

An application structure should consist of the following directories:

`textbook/`
|
|_ _ _ `textbook.php` (Main application engine file)
|_ _ _ `textbook.xml` (Application Manifest file)
|_ _ _ `assets/`
|_ _ _ `assets/icons/` (Stores the icon of the app)
|_ _ _ `assets/icons/small.png` (The app icon 16x16)
|_ _ _ `assets/icons/large.png` (The app icon 32x32)
|_ _ _ `config/`
|_ _ _ `config/user.json` (User's configuration manifest)
|_ _ _ `config/admin.json` (Administrator's configuration manifest)
|_ _ _ `widgets/` (Contains a list of widget views)
|_ _ _ `views/` (Contains a list of widget views)


<a href="/files/developers/app_sample.zip" class="btn btn-success""><i class="icon-download"></i> &nbsp; Download Sample App</a>   <a href="/developers/applications/manifest_file" class="btn btn-primary"">Start Documentation &rarr;</a>

If you are already well versed with the manifest file, you may skip to the following sections:

<a href="#">Documentation for Application Triggers &rarr;</a>

<a href="#">Documentation for Application Views &rarr;</a>

<a href="#">Documentation for Application Widgets &rarr;</a>