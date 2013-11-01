The conversation's data api allows you to easily embed a link on your extension and allow other users to click on it to start a conversation with another user.


## data-es-conversations-compose
The `data-es-conversations-compose` data api allows you to display the html code for users to start a conversation.

```php

require_once( JPATH_ROOT . '/administrator/components/com_easysocial/includes/foundry.php' );

// Render css codes
Foundry::document()->init();

// This will render the necessary javascripts on the page header.
Foundry::page()->processScripts();
?>

<a href="javascript:void(0);" 
	data-es-conversations-compose 
	data-es-conversations-id="<?php echo $userId;?>"
	data-es-conversations-listid="<?php echo $listId;?>"
><?php echo JText::_( 'Start Conversation' ); ?></a>

```

### Attributes Explained

`data-es-conversations-compose` (Required) - This is a required data attribute.
`data-es-conversations-id` - This is the user's id that you would like to start a conversation with.
`data-es-conversations-listid` - If you need to start a group conversation, provide the friend list id here.