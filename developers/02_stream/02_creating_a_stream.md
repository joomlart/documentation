Creating a stream record should be done within your own extension. Ideally, it should be placed in a central location where CRUD happens. 

Each stream is tied to an `actor`, `context` and a `verb`. 

## Creating The Stream Record
To create a basic stream record, it only takes a couple of lines:

```php
// This is the main engine file of EasySocial
require_once( JPATH_ROOT . '/administrator/components/com_easysocial/includes/foundry.php' );


// Retrieve the stream library.
$stream 	= Foundry::stream();


// Retrieve the stream template.
$template 	= $stream->getTemplate();


// @required
// Set the actor that is generating this stream item.
$template->setActor( int $actorId , string $actorType );


// @required
// Set the context type of this stream item.
$template->setContext( int $contextId , string $contextType );


// @required
// Set the verb / action for this stream item.
// Example verbs: add, edit , create , update , delete.
$template->setVerb( string $verb );


// @optional
// Set the target item. This is usually needed if you are targeting an object
// Example targets: Adam posted an update on Jennifer's profile. The $targetId would be Jennifer's id.
$template->setTarget( int $targetId );


// @optional
// Set the type of the stream, whether it should be rendered in full mode or mini mode.
// Mini mode does not have a header and does not actions on the stream.
// Example types: full,mini
$template->setType( string $type );


// @optional
// If you do not plan to create an application to manipulate the stream, you may specify the title here.
// Example: "Jennifer created a new textbook."
$template->setTitle( string $title );


// @optional
// If you do not plan to create an application to manipulate the stream, you may specify the contents of the stream here.
// Example: "Some descriptions of the book."
$template->setContent( string $content );


// @optional
// You may also specify that stream items should be available site wide to everyone like a broadcast message.
// Example: "Hello everyone, this is a custom message."
$template->setSideWide( boolean $state );


// @optional
// You may also bind a location to the stream item if you utilize the location library.
$template->setLocation( SocialTableLocation $location );


// @optional
// You may also tag other users in the stream by supplying the user id's.
// Example: array( 62,63,64);
$template->setWith( mixed $userIds );


// @optional
// You can also specify the option to aggregate your stream items. If you have multiple sources but only want to generate a single stream item.
$template->setAggregate( boolean $aggregation );


// @optional
// This allows you to set a custom creation date for the stream item. It must be in MySQL date format.
// Example: 2013-01-01 12:00:00
$template->setDate( string $dateString )
```

Methods breakdown:

`setActor`:

`setContext`:

`setVerb`:

`setTarget`:

`setType`:

`setTitle`:

`setSiteWide`:

`setLocation`:

`setWith`:

`setAggregate`:

`setDate`:



## Example: Uploading a new photo
This is an example of stream creation when a user uploads a new photo.

```php
$my 		= Foundry::user();
$stream 	= Foundry::stream();
$template 	= $stream->getTemplate();


$template->setActor( $userId , 'user' );

$template->setContext( $photoId , 'photos' );

$template->setVerb( 'add' );

// We use the album id as target because the user is adding the photos in the album.
$template->setTarget( $albumId );

// We want to display the stream item in full mode.
$template->setType( 'full' );


// When we are done with the template, add it through the stream.
$stream->add( $template );

```


## Example: Broadcasting a new mesasge
This is an example of creating a new broadcast message that is visible to everyone on the site.

```php

$my	 		= Foundry::user();
$stream		= Foundry::stream();
$template 	= $stream->getTemplate();

$template->setActor( $my->id , 'user' );

$template->setContext( $broadcast->message , 'broadcast' );

$template->setVerb( 'create' );

$template->setSideWide( true );

$stream->add( $template );

```


