With applications, you could also build widgets around the profile and the dashboard area. Widgets are basically small chunk of codes that appears on a user profile or a dashboard.

To create a widget view, you need to create a `widgets` folder in your application.

`textbook/`
|
|_ _ _ `widgets/` (Contains a list of widget views)
|_ _ _ `widgets/profile/view.html.php` (Responsible to output profile widgets)
|_ _ _ `widgets/dashboard/view.html.php` (Responsible to output dashboard widgets)


## Widget File
The widget file which is named `view.html.php` is almost identical to a Joomla view file. With the exception that it doesn't have a `tmpl` folder. However, you can choose to either use our built-in theme functionality or provide your own set of method to output the contents.

## Example: Profile Widget

```php
defined( '_JEXEC' ) or die( 'Unauthorized Access' );


class TextbookWidgetsProfile extends SocialAppsWidgets
{
	/**
	 * This will display a simple "Hello World" message on the person's profile sidebar.
	 *
	 * @param 	SocialUser	The user object.
	 * @return	null
	 */
	public function sidebarTop( SocialUser &$user )
	{
		echo "Hello World";
	}
	
}

```

## Example: Dashboard Widget

```php
defined( '_JEXEC' ) or die( 'Unauthorized Access' );


class TextbookWidgetsDashboard extends SocialAppsWidgets
{
	/**
	 * This will display a simple "Hello World" message on the person's dashboard sidebar.
	 *
	 * @param 	SocialUser	The user object.
	 * @return	null
	 */
	public function sidebarTop( SocialUser &$user )
	{
		echo "Hello World";
	}
	
}

```


## Widget Positions
Widgets also have positions that is similar to modules. Widgets however have greater control and is aware of the current user that is being accessed.

### Available Positions:

Profile:

`aboveHeader` - Appears on the user's profile above the header.
`sidebarBottom` - Appears on the user's profile sidebar at the bottom.
`sidebarTop`  - Appears on the user's profile sidebar at the top.
`afterBadges` - Appears on the user's profile after the badges.
`beforeBadges` - Appears on the user's profile before the badges.
`afterActions` - Appears on the user's profile after the actions.
`beforeActions` - Appears on the user's profile before the actions.
`afterInfo` - Appears on the user's profile after the info.
`afterAvatar` - Appears on the user's profile after the avatar.
`afterName` - Appears on the user's profile after the name.
`beforeName` - Appears on the user's profile before the name.

Dashboard:

`sidebarTop` - Appears on the user's dashboard sidebar at the top.
`sidebarBottom`- Appears on the user's dashboard sidebar at the bottom.