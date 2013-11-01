EasySocial comes with a wide variety list of libraries that you as an extension developer or 3rd party application developer could make use of. The base of EasySocial relies on our very own `Foundry` engine. It's the heart of EasySocial.



## Foundry Framework
Foundry framework is basically the heart of the extension. Every function or classes routes through the PHP's `Foundry` library. In order for you to access a library in EasySocial, you would need to utilize the `Foundry` object.


### Retrieving a user object
Example:

```php 
require_once( JPATH_ROOT . '/administrator/components/com_easysocial/includes/foundry.php' ); 

// Retrieves the current logged in user object.
$user	= Foundry::user();
```


### Retrieving an Oauth library
Example:

```php
require_once( JPATH_ROOT . '/administrator/components/com_easysocial/includes/foundry.php' );

// Retrieves the oauth library.
$oauth	= Foundry::oauth( 'Facebook' );

echo $oauth->getLoginButton();
```

### Retrieving the apps library
Example:

```php
require_once( JPATH_ROOT . '/administrator/components/com_easysocial/includes/foundry.php' );

// Retrieves the apps library.
$lib 	= Foundry::apps();
```



## Available libraries

* `access`
* `ajax`
* `akismet`
* `albums`
* `alert`
* `apps`
* `assets`
* `avatar`
* `badges`
* `bbcode`
* `captcha`
* `comments`
* `config`
* `connector`
* `contentparser`
* `conversations`
* `cover`
* `crawler`
* `cron`
* `date`
* `db`
* `debug`
* `dispatcher`
* `exif`
* `fields`
* `form`
* `friends`
* `geocode`
* `image`
* `indexer`
* `info`
* `installer`
* `javascript`
* `json`
* `language`
* `less`
* `likes`
* `location`
* `mailer`
* `maintenance`
* `maps`
* `migrators`
* `uploader`
* `user`