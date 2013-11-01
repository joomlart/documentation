Once the rules are properly initialized, all you need to do is to add the respective codes below to log the actions that the user performed so that EasySocial would know when to assign the badge to the user.


## Logging Points Actions
Every time the user performs a specific action, your extension could include the codes below to log a point record for the user:


```php
require_once( JPATH_ROOT . '/administrator/components/com_easysocial/includes/foundry.php' );

// @points: photos.upload
Foundry::points()->assign( 'textbook.create' , 'com_easysocial' , $userId );
```