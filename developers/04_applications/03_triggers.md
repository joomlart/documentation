Every application that is created must consist of at least a single php file which is the main element name. For an instance, if your app is called `textbook`, your directory structure should be of the following:

`textbook`/
|
|_ _ _ `textbook.php` (Main application engine file)
|_ _ _ `textbook.xml` (Manifest file)

The main application engine file `textbook.php` should be responsible to house all of the triggers. This is the place where our library would be searching for.

## Available Triggers
The following are the available triggers in any applications of EasySocial:


`onPrepareStream` - 

`onNotificationLoad` - 

`onAfterCommentSave` - 

`onAfterLikeSave` - 

`hasAppListing` - 


## onPrepareStream
The `onPrepareStream` trigger allows an application to manipulate the stream object before getting processed and displayed on the screen.

Examples of usage:

* Your extension creates a new stream record but the application may alter the contents of the stream or generate contents for the stream.
* You have a word censor plugin to censor words on the stream.


Code Example:

```php
public function onPrepareStream( SocialStreamItem &$stream, $includePrivacy = true )
{
	// Perform application logics here.
}
```

## onNotificationLoad
The `onNotificationLoad` trigger allows an application to manipulate the notification that before getting processed and displayed in the notifications list.

Examples of usage:

* Your application wants to display a video on the notification dropdown.

```php
public function onNotificationLoad( SocialTableNotification &$item )
{
	// Perform application logics here.
}
```

## onBeforeCommentSave

## onAfterCommentSave
The `onAfterCommentSave` trigger allows an application to manipulate the comment after it gets stored into the database.

Examples of usage:

* Your application synchronizes with your own comment extension.


Code Example:

```php
public function onAfterCommentSave( SocialTableComments &$comment )
{
	// Perform application logics here.
}
```

## onBeforeLikeSave

## onAfterLikeSave
The `onAfterLikeSave` trigger allows an application to manipulate the likes state before and after it gets stored into the database.

Examples of usage:

* Your application synchronizes the likes on a stream with Facebook.


Code Example:

```php
public function onAfterLikeSave( SocialTableLikes $likes )
{
	
	// Perform application logics here.
	
}
```


## hasAppListing 
The `hasAppListing` trigger allows an application to let the system know dynamically if the application should appear in the application listings on the profile or dashboard page.

Example: Your application allows the user to configure application behavior whether it should appear on the profile app listings or not.


```php
public function hasAppListing( string $view )
{
	$params 	= $this->getParams();
	
	// We only want to display the app on the dashboard.
	if( !$params->get( 'display_profile' ) && $view == 'profile' )
	{
		return false;
	}
	
	return true;
}
```