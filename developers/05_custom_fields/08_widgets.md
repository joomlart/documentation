Similar like [application widgets](/developers/applications/widgets) , it is also possible to define and publish fields in selective positions on the site. You could build really cool field widgets that displays itself on a profile or in the dashboard.

A custom field widget should contain a structure of the following

`textbox/`
|
|_ _ _ `widgets/` (The system would look for widget views here)
|_ _ _ `widgets/profile` (This determines that the widget is available for the profile)
|_ _ _ `widgets/profile/view.html.php` (This is the main file the system would look for)


Code Example:

```php
class TextboxFieldWidgetsProfile
{
	// The function name would be dependent on the position of the field.
	public function profileHeaderA( $key , $user , $field )
	{
	}
}
```