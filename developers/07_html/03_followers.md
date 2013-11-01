The friend's data api allows you to easily embed a link on your extension and allow other users to add the person as a friend on the site.


## data-es-friends-add
The `data-es-friends-add` data api allows you to display the html code for users to add another person as their friend.

```php

require_once( JPATH_ROOT . '/administrator/components/com_easysocial/includes/foundry.php' );

// This will render the necessary javascripts on the page header.
Foundry::page()->processScripts();
?>

<a href="javascript:void(0);" data-es-friends-add data-es-friends-id="<?php echo $userId;?>"><?php echo JText::_( 'Add as friend' ); ?>

```

## data-es-friends-cancel
The `data-es-friends-cancel` data api allows you to display the html code for users to cancel an existing friend request.

## data-es-friends-reject
The `data-es-friends-reject` data api allows you to display the html code for users to cancel an existing friend request.

## data-es-friends-approve
The `data-es-friends-approve` data api allows you to display the html code for users to cancel an existing friend request.

## data-es-friends-delete