This is the heart of the field application and where everything is rendered from. The field application will have to follow a convention [file name](#filename), [class name](#classname), [basic triggers](#basictriggers) and also the [available properties](#availableproperties).

At the end of this documentation is a full list of the [available triggers](#availabletriggers). The triggers are not mandatory and you only need to choose those that are applicable to your field.

A field is mainly identified by 2 keys, `group` and `element`. Currently EasySocial only supports the group __user__.

<a name="filename"></a>
## File name

The field application must consist of the main application file that contains all the trigger functions. The file name follows the field's element name.

`element`/  
|  
|_ _ _ `element.php`

<a name="classname"></a>
## Class name

The main class should follow the convention format of `SocialFields<Group><Element>` and the class should extend the class `SocialFieldItem`.

E.g. if your field element name is textbox, then the class definition should be:

	class SocialFieldsUserTextbox extends SocialFieldItem {}

<a name="basictriggers"></a>
## Basic triggers

_Refer to [available triggers](#availabletriggers) for the full listing of triggers and arguments that it accepts._

On the very bare, your field should at least consist of 4 triggers for it to work properly:

* onRegister
* onEdit
* onDisplay
* onSample

These are the main triggers that displays your field in 4 different views.

The trigger will have to call `$this->display()` at the end of the function to render the field.

Refer to [Field themes and output](field_output) for information on field theme rendering and handling.

### onRegister

This is mainly responsible for rendering the field during a user registration.

### onEdit

This is mainly responsible for rendering the field when a user edits his/her own profile.

### onDisplay

This is mainly responsible for rendering user data on a user's profile info page.

### onSample

This is mainly responsible for rendering a sample output of the field in the backend when an admin is configuring the profile's custom fields.

__Sample codes__

	public function onRegister (&$post, &$registration) {
		return $this->display();
	}

	public function onEdit (&$post, &$user) {
		return $this->display();
	}

	public function onDisplay (&$post, &$user) {
		return $this->display();
	}

	public function onSample () {
		return $this->display();
	}

<a name="availableproperties"></a>
## Available properties

When your field class is loaded, these are the properties ready and loaded to be used in the class:

* `$event` - string - The event/trigger name.
* `$element` - string - The field's element name.
* `$group` - string - The field's group.
* `$field` - SocialTable/JTable - The field table object.
* `$params` - SocialRegistry/JRegistry - The field configuration parameter in registry.
* `$value` - string - The stored raw data in string of the current user.
* `$inputName`- string - The unique identifier of the field.

<a name="availablemethods"></a>
## Available methods

### display

This is the main method that displays the appropriate content (depending on the field's theme file) based on the current trigger. If a template name is passed in, then it will render the template file.

	string display ( string $template = null )

### allowedPrivacy

This method checks the privacy of the user with the current view. This is mainly used in `onDisplay` to decide if the viewing user have the permission to view the data.

	bool allowedPrivacy ( SocialUser $user )

### escape

This method escapes an input string from user and returns a safe string that prevents security issues.

	string escape ( string $text )

### getOptions

This method returns the available options based on the configuration parameter name that you've defined in the [field configuration file](field_configuration) for the types of `select/dropdown/list`, `checkbox` and `choices`.

	array getOptions ( string $key = null )

### setError

	void setError ( string $message = null )

### hasError

	bool hasError ()

### getError

	string getError ()


<a name="availabletriggers"></a>
## Available triggers

### Register

These triggers are responsible for registration process.

	onRegister (array &$post, SocialTableRegistration &$registration)
	
	onRegisterValidate (array &$post, SocialTableRegistration &$registration)
	
	onRegisterBeforeSave (array &$post, SocialUser &$user)

	onRegisterAfterSave (array &$post, SocialUser &$user)

	onRegisterAfterSaveFields (array &$post, SocialUser &$user)

	onRegisterOauthBeforeSave (array &$post, SocialOauth &$client)

	onRegisterOauthAfterSave (array &$post, SocialOAuth &$client, SocialUser &$user )

### Edit

These triggers are responsible for a user editting his own profile. These are also the fallback triggers for AdminEdit.

	onEdit (array &$post, SocialUser &$user)

	onEditValidate (array &$post, SocialUser &$user)

	onEditBeforeSave (array &$post, SocialUser &$user)

	onEditAfterSave (array &$post, SocialUser &$user)

	onEditAfterSaveFields (array &$post, SocialUser &$user)

### AdminEdit

These triggers are responsible for an admin editting a user in the backend. If these triggers does not exist, it will fallback to "Edit" triggers.

	onAdminEdit (array &$post, SocialUser &$user)

	onAdminEditValidate (array &$post, SocialUser &$user)

	onAdminEditBeforeSave (array &$post, SocialUser &$user)

	onAdminEditAfterSave (array &$post, SocialUser &$user)

	onAdminEditAfterSaveFields (array &$post, SocialUser &$user)

### Sample

This trigger is responsible for rendering a field sample for administrator to view in the backend during profile configuration.

	onSample

### Display

This trigger is responsible to render the field data in user's profile info page.

	onDisplay (SocialUser $user)

### Misc

	onCronExecute

	onIndexer (string $userFieldData)

	onIndexerSearch (int $userId, string $keywords, string $userFieldData)

	onFriendSuggestSearch (SocialUser $user, string $userFieldData)