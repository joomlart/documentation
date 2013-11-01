Accessing a database layer is pretty identical to the standard method that Joomla uses to retrieve the database object.

Example:

``` php
require_once( JPATH_ROOT . '/administrator/components/com_easysocial/includes/foundry.php' );

// Retrieves the database obejct
$db 	= Foundry::db();
$sql 	= $db->sql();

// Retrieves a user object from the database with the user id of 42.
$sql->select( '#__users' );
$sql->where( 'id' , 42 );

$db->setQuery( $sql );

$data	= $db->loadObject();
```