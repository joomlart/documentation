Application views allows your application to be rendered on a person's dashboard or a profile or both. The purpose of displaying them on the profile is to allow other users to view items that the user has recently created. 

Each application that you create must be a derived class from the base application class, `SocialAppsItem`.


## Available Views
There are currently 2 views available (As of the date of writing this documentation). They are:

* `Profile View` - The purpose of this view is to display information about a user.
* `Dashboard View` - The purpose of this view is like a home for the current logged in user.

## View Types
Along with the available views, you can also decide on a view type in your application XML file. You may use the following xml declaration for your views:


```php

<views>
	<view type="canvas">dashboard</view>
	<view type="embed">profile</view>
</views>
	
```

`canvas` - Canvas view type displays the app on it's own page. It does not render the contents on the profile or dashboard page.

`embed` - An embed view will trigger ajax calls to the server to retrieve the contents of your app without a page refresh.



## Profile View
Profile views allows your application to display contents on a profile. To create a profile view, you will need the following:

1. Declaration in the manifest file. (You may also use `canvas` type if you want a full screen)


```php

<views>
	<view type="embed">profile</view>
</views>
	
```


2. The main profile view file.

To create a profile view file, it needs to follow the directory hierarchy as shown below:

`textbook/`
|
|_ _ _ `views/` (Contains a list of widget views)
|_ _ _ `views/profile` (This tells the system that you are building a profile view)
|_ _ _ `views/profile/view.html.php` (The main file)

The `view.html.php` should contain the codes below:

```php
defined( '_JEXEC' ) or die( 'Unauthorized Access' );

class TextbookViewProfile extends SocialAppsView
{
	// This is the main method and it is required.
	public function display( int $userId )
	{
		// Perform application logics here.
	}
}
```

## Dashboard View
Dashboard view allows your application to display contents within the user's dashboard. To create a dashboard view, you will need the following:

1. Declaration in the manifest file. (You may also use `canvas` type if you want a full screen)


```php

<views>
	<view type="embed">dashboard</view>
</views>
	
```


2. The main dashboard view file.

To create a dashboard view file, it needs to follow the directory hierarchy as shown below:

`textbook/`
|
|_ _ _ `views/` (Contains a list of widget views)
|_ _ _ `views/dashboard` (This tells the system that you are building a dashboard view)
|_ _ _ `views/dashboard/view.html.php` (The main file)

The `view.html.php` should contain the codes below:

```php
defined( '_JEXEC' ) or die( 'Unauthorized Access' );

class TextbookViewDashboard extends SocialAppsView
{
	// This is the main method and it is required.
	public function display( int $userId )
	{
		// Perform application logics here.
	}
}
```