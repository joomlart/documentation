The `Users` object in EasySocial is decorated with rich functionality that allows you to quickly access multiple properties of the user. In essence, loading a user object is as simple as:

```php
require_once( JPATH_ADMINISTRATOR . '/components/com_easysocial/includes/foundry.php' );

// Get the current logged in user
$my 	= Foundry::user();

// Retrieve a specific user given it's id.
$user 	= Foundry::user( $id );

```

## Retrieving User's Name
It is possible that the site admin configures EasySocial to use `username` instead of `real name` as the display name or vice versa. Your extension should always rely on `getName` to retrieve the user's name.

Example:

```php
$my 	= Foundry::user();
echo $my->getName();

// Shorter way of writing it
echo Foundry::user()->getName();

// Getting another person's name
echo Foundry::user( $id )->getName();
```

## Retrieving Stream Name
There are times when you don't want to display the name of the user but instead you want to use terminologies such as `You` when the user is viewing his own item. You can invoke the method below:

```php
$my 	= Foundry::user();

$my->getStreamName();
```

## Retrieving User Avatar
To retrieve an avatar of a user, its
```php
$my	= Foundry::user();
?>
<img src="$my->getAvatar();" />
```

Arguments:

`$avatarSize` - (Optional) If specified, it uses the size provided.

### Avatar Sizes
These are available sizes and it's dimension


`SOCIAL_AVATAR_SMALL` - Smallest version of avatar. Dimensions: 32 x 32
`SOCIAL_AVATAR_MEDIUM` - Medium version of avatar. Dimensions: 64 x 64
`SOCIAL_AVATAR_SQUARE` - Large square version of avatar. Dimensions: 180 x 180
`SOCIAL_AVATAR_LARGE` - Large version of avatar. Dimensions: 180x (y) (This is a proportionate size)


## Retrieving User Cover
To retrieve a user's cover, you may use the codes below:
<a id="getCover"></a>

```php
$my 	= Foundry::user();

// Cover is a photo object
$photo	= $my->getCover();

// Output the cover source.
echo $cover->getSource( 'large' );

// Shorthand
echo $my->getCover()->getSource( 'large' );
```

## Retrieving User's Profile
To retrieve a user profile, you may use the codes below:
<a id="getProfile"></a>

```php
$my	= Foundry::user();

// Retrieve the user's profile object
$profile 	= $my->getProfile();
```

## Retrieving User's Privacy
To retrieve the privacy object of a user, you may use the codes below:
<a id="getPrivacy"></a>

```php
$my	= Foundry::user();

// Retrieve the user's privacy object
$privacy 	= $my->getPrivacy();
```

## Retrieving Total Followers
To retrieve the total number of followers a user has, you may use the codes below:
<a id="getTotalFollowers"></a>

```php
$my	= Foundry::user();

$my->getTotalFollowers();
```

## Retrieving Total Following
To retrieve the total number of people the user is following, you may use the codes below:
<a id="getTotalFollowing"></a>

```php
$my	= Foundry::user();

$my->getTotalFollowing();
```


## Retrieving Total Friends
To retrieve the total number of friends the user has, you may use the codes below:
<a id="getTotalFriends"></a>

```php
$my	= Foundry::user();

$my->getTotalFriends();
```

## Retrieving Total Albums
To retrieve the total number of albums a user has, you may use the codes below:
<a id="getTotalFriends"></a>

```php
$my	= Foundry::user();

$my->getTotalAlbums( bool $excludeCore );
```

Arguments:

`$excludeCore` - (Optional) Boolean flag to determine if it should exclude core albums such as (profile photos, cover photos, story photos).


## Retrieving Total Points
To retrieve the total points a user has, you may use the codes below:
<a id="getPoints"></a>

```php
$my 	= Foundry::user();

$points = $my->getPoints();
```


## Retrieving Total Badges
To retrieve the total number of badges a user has, you may use the codes below:
<a id="getTotalBadges"></a>

```php
$my 	= Foundry::user();

$total 	= $my->getTotalBadges();
```

## Retrieving Total Friend's List
To retrieve the total number of friend's list a user has, you may use the codes below:
<a id="getTotalFriendsList"></a>

```php
$my 	= Foundry::user();

$total 	= $my->getTotalFriendsList();
```

## Retrieving Total New Notifications
To retrieve the total number of new notifications a user has, you may use the codes below:
<a id="getTotalFriendsList"></a>

```php
$my 	= Foundry::user();

$total 	= $my->getTotalNewNotifications();
```

## Retrieving Total New Conversations
To retrieve the total number of new conversations a user has, you may use the codes below:
<a id="getTotalFriendsList"></a>

```php
$my 	= Foundry::user();

$total 	= $my->getTotalNewConversations();
```

## Retrieving Total New Friend Requests
To retrieve the total number of friend requests a user has, you may use the codes below:
<a id="getTotalFriendRequests"></a>

```php
$my 	= Foundry::user();

$my->getTotalFriendRequests();
```


## Retrieving List of Badges
To retrieve the list of badges a user has achieved, you may use the codes below:
<a id="getBadges"></a>

```php
$my 	= Foundry::user();
$badges	= $my->getBadges();


// Loop through each of the badges
if( $badges )
{
	foreach( $badges as $badge )
	{
		echo '<img src="' . $badge->getAvatar() . '" />';
	}
}
```

## Retrieving List of Apps
To retrieve the list of apps a user has installed, you may use the codes below:
<a id="getApps"></a>

```php
$my 	= Foundry::user();

$apps 	= $my->getApps( string $view );

```

Arguments:

`$view` - (Required) This determines the view that app should appear.


## Testing If User is Viewer
At times, you want to test if the current viewer is the user that is being accessed.
<a id="isViewer"></a>

Example:

```php
$user 	= Foundry::user( $id );

if( $user->isViewer() )
{
	// Do something if the user is a viewer.
	echo "Hello, you are accessing your own item!";
}
```


## Approving A User
If you are handling your own user registrations, you may invoke the following method to approve a user.
<a id="approve"></a>

```php

$user 	= Foundry::user( $id );
$user->approve( bool $sendEmail )

```

Arguments:

`$sendEMail` - (Optional) If this is not specified, it is defaulted to send the user a notification e-mail.


## Rejecting A User
If you are handling your own user registrations, you may invoke the following method to reject a user.
<a id="reject"></a>

```php

$user 	= Foundry::user( $id );
$user->approve( strng $message = '' , bool $sendEmail = true , bool $deleteUser = false )

```

Arguments:

`$message` - (Optional) If there's a message specifying the reason of rejecting this user.
`$sendEMail` - (Optional) If this is not specified, it is defaulted to send the user a notification e-mail.
`$deleteUser` - (Optional) Boolean flag to determine if the system should also delete the user.


## Assigning User to Joomla User Group
To assign a user into a specific Joomla user group, you may use the codes below:
<a id="assign"></a>

```php
$user 	= Foundry::user( $id );

$user->assign( int $groupId );
```


## Determining if a user is blocked
To determine if a user is blocked on the site, you may use the codes below:

```php
$my 	= Foundry::user();

if( $my->isBlock() )
{
	// Do something here
}
```


## Determining if a user is currently online
To determine if the user is currently online or not, you may use the codes below:

```php
$user 	= Foundry::user($id);

if( $user->isOnline() )
{
	// Target user is currently online, display a chat button.
}
```

## Determining if the user is a site admin
EasySocial checks against the `core.admin` ACL rule in Joomla in determining if the user is a site administrator or not. To determine if the user is a site admin, you may use the codes below:

```php
$my 	= Foundry::user();

// Returns true / false
if( $my->isSiteAdmin() )
{
	// Display secret menu.
}
```

## Determining if user is a friend with another user
To be able to determine if the user is a friend of another user, you may use the codes below:

```php
$my 	= Foundry::user();

$my->isFriends( $targetUserId );
```

## Logging out a user
To logout a user from the site, you may use the codes below:

```php
$my 	= Foundry::user();

$my->logout();
```





















