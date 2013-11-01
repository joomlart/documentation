Once the rules are properly initialized, all you need to do is to add the respective codes below to log the actions that the user performed so that EasySocial would know when to assign the badge to the user.


## Logging Achievement Actions
Logging achievement actions is pretty easy. All you need to do is to embed the 2 liner code below in your own extension logic:


```php
require_once( JPATH_ROOT . '/administrator/components/com_easysocial/includes/foundry.php' );

// @badge: textbook.create
Foundry::badges()->log( 'com_textbook' , 'textbook.create' , $userId , JText::_( 'Created a new textbook.' ) );
```

Yep, it's just as simple as that :) Just repeat all the actions throughout your extension.