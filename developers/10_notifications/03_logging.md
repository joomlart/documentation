Once the alert rules are properly initialized and installed, you will then need to create the logging mechanism to log down new notification items. The notification system in `EasySocial` allows you to notify via e-mail or via the internal notification system. 


## Internal Notifications
In this example, it will trigger `EasySocial` to perform an internal notification to the target user:


```php
		// Internal notification options
		$options	= array(
								'uid'			=> $article->id,
								'title'			=> 'Some title here',
								'actor_id'		=> $actor->id,
								'target_id'		=> $recipient->id,
								'context_ids'	=> "article",
								'context_type'	=> $type,
								'url'			=> JRoute::_( 'index.php?option=com_content' )
							);

		$emailOptions = array();


		// Send notification to the target
		$state 		= Foundry::notify( $cmd , array( $userId ) , $emailOptions , $options );
		
```

### Params

`$cmd` 		- (Required) This should be the same command that is defined in the rule file
`$userId` 	- (Required) This should be the target user id.
`$emailOptions` - (Optional) Only needed if you want to notify via e-mail.
`$options` - (Required) Needed to generate an internal notification.

### Options

`uid` 			- (Required) This represents the unique id of the item.
`title`			- (Required) This represents the title of the notification item. E.g: "Alejandro posted on your timeline."
`actor_id`		- (Optional) Allows you to populate the title with {actor}
`target_id`		- (Optional) Allows you to populate the title with {target}
`context_type`	- (Required) This is the context type and should be your application element name.
`url`			- (Required) The user will be redirected to this url as soon as they click on the notification item.

## Email Notifications
Coming soon.