There are times when your extension wants to delete a stream item. This is often the case when your item is deleted from the site and you do not want any stream item related to this item to still be available on the stream.

To delete a stream item, it only takes a single line of code to remove an item. However, your code must be aware of the context that it is trying to delete.

## Example
For instance, when a photo is deleted from the site, the following codes are fired:

```php
require_once( JPATH_ROOT . '/administrator/components/com_easysocial/includes/foundry.php' );

Foundry::stream()->delete( $photoId , 'photos' );
```

Arguments:

`contextId` - This is the first argument that the method accepts. It should be the context id of the item that you are trying to remove.

`contextType` - This should be the context type of the item that you are trying to remove.

`userId` (Optional) - If you only need to remove from specific users, supply the user id here.
