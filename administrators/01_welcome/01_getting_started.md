## Requirements
Before we begin, ensure that you have met the [System Requirements](/setup/system_requirements) in order for EasySocial to operate correctly. You may find the most basic requirements for EasySocial below:

### Joomla!
EasySocial requires that you have Joomla! installed on the site. EasySocial supports the following versions of Joomla!:

* `Joomla 1.6+`
* `Joomla 1.7+`
* `Joomla 2.5+`
* `Joomla 3.0+`

###PHP Requirements
EasySocial runs on PHP and it requires PHP to exist on the site.

* `5.2+` and above.
* `ZIP` Library. Much faster extraction process.
* `GD` Library. In order to manipulate images that are uploaded on the site.
* `CURL` Library. In order for EasySocial to perform outgoing connections.


### PHP Settings
| Settings     | Minimum | Recommended | Reason |
| ------------ | :-------------: | :------------: | ------------ |
| memory_limit | 64MB | 128MB | For image manipulation |
| upload_max_filesize | 8MB | 32MB | It determines the size of files that can be uploaded on the site. |
| post_max_size | 8MB | 32MB | It determines the size of files that can be uploaded on the site. |
| magic_quotes_gpc | Off | Off | On Joomla 3 and above, this needs to be explicitly disabled as per Joomla's requirements. |


###MySQL Requirements
EasySocial requires a minimum version of `MySQL 4.1+` 



## Checking System Requirements
Joomla! provides system administrator's an extremely simple method to check the your system requirements. These options are available through `System` > `System Information`


You can also create a very simple PHP script and include the codes below in your php file.

```php
<?php
// This is a very simple method to load up php's settings.
phpinfo();
?>
```


## Recommended Hosting Providers
We have ran a couple of tests on these hosting providers and we recommend them because we've ran a couple of tests on them and they seem to be pretty good at it. (At your own risk)

* [CloudAccess](http://cloudaccess.net) - Official Joomla! demo provider. They know what they are doing.
* [SiteGround](http://siteground.com) - Optimized to run on Joomla! sites.
* [Rackspace](http://rackspace.com) - Pretty good support and fast.
