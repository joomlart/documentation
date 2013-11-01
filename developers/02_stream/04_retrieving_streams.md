There are times when your extension wants to render the stream data from EasySocial. With the API in EasySocial, this is possible and it's pretty easy too.


### Example
To retrieve stream items, you only need to execute the codes below:


```php
require_once( JPATH_ROOT . '/administrator/components/com_easysocial/includes/foundry.php' );

$data = Foundry::stream()->get( $options );
```

The `$options` in the sample above is supported with the following indexes:


`$options['userId']` : Require when you only want to retrieve streams from a particular user.  
`$options[ 'listId']` : Require when you want to retrive streams from a friend list.   
`$options[ 'context' ]` : Display the stream from certain context ( app ). Default is 'all'.
`$options[ 'type' ]` : Specify the actor type. Default is 'user'.   
`$options[ 'limitStart' ]` : Specify the start limit of the stream retrieval. In date format string   
`$options[ 'limitEnd' ]` : Specify the send limit of the stream retrieval. In date format string.  
`$options[ 'direction' ]` : To get 'older' stream or 'later' stream. Default is 'older'.   
`$options[ 'viewerId' ]` : The current viewing user. If null passed in, the current login user id will be used.    




E.g. Get stream from a user:  


```php
$options 	= array(
				'userId' 		=> '43',
				'context' 		=> 'all',
				'type' 			=> 'user',
				'limitStart' 	=> '2013-10-01 01:59:59',
				'limitEnd' 		=> '2013-09-31 01:59:59'
				);
				
$stream->get( $options );


```

	
E.g. Get stream from a friend list:

```php
$options 	= array(
				'listId' 		=> '2',
				'context' 		=> 'all',
				'type' 			=> 'user',
				'limitStart' 	=> '2013-10-01 01:59:59',
				'limitEnd' 		=> '2013-09-31 01:59:59'
				);
				
$stream->get( $options );
```

E.g. Get stream from followed profile users.

```php
$options 	= array(
				'context' 		=> 'all',
				'type' 			=> 'follow',
				'limitStart' 	=> '2013-10-01 01:59:59',
				'limitEnd' 		=> '2013-09-31 01:59:59'
				);
				
$stream->get( $options );
```
