To manipulate a stream output, you will first need to create an [application](/developers/applications/getting_started) for  EasySocial. Your application can just be created to manipulate streams as there is no requirements for applications to be displayed on a profile.

Once you have already created your application, you will need to create a method in your application engine file.

## Example
If your application element is called `textbook`, you will need to create the function below in the `textbook.php` file.

```php
public function onPrepareStream( SocialStreamItem &$item , $includePrivacy = true )
{
	
	// Since every stream item is triggered, we only want to process known context.
	if( $item->context != 'textbook' )
	{
		return;
	}

	// Get the actor of the stream item. This is a SocialUser object.
	$actor 	= $stream->actor;
	
	// Get the verb of the stream item since we need to have different outputs based on the verb.
	$verb 	= $stream->verb;
	
	if( $verb == 'add' )
	{
		// Set the title of the stream
		$stream->title 		= JText::sprintf( '%1s created a new textbook' , $actor->getName() );
		
		// We want to display the contents of the textbook
		$stream->content 	= JText::_( 'This is some description of the book that the actor have just created!' );
	}
	
	
	
}
```