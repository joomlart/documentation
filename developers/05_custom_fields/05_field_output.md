Field outputs are needed from 5 triggers:

* onRegister
* onEdit
* onAdminEdit
* onSample
* onDisplay

_Refer to [triggers documentation](triggers) for full list of triggers and method to render the field output._

## Field template hierarchy

The fields expect at least content.php file to exist in the themes folder. While content.php will be the bare essentials and commonly shared theme file, you can define theme files according to the template hierarchy to have different output for different triggers.

EasySocial will follow the following order to look for files, given a trigger: on\<Event\>, the loading order will be:

1. \<event\>.php
2. \<event\>_content.php
3. content.php

For example, the trigger onRegister, will have a loading order of:

1. register.php
2. register_content.php
3. content.php

This applies to all 5 rendering triggers listed above, with a special case of "onAdminEdit" falling back to "onEdit" if it does not exist.

We suggest that you should either use content.php for commonly used template file if possible to share the same output accross all trigger. This will minimize the code changes and design on your part.

If different output is needed for some of the triggers, then you can have file set of:

* register_content.php
* content.php

In such case, `onRegister` trigger will render the file `register_content.php`, while the other triggers will render the file `content.php`.


## Template differences

![Template differences](/images/developers/05_custom_fields/field_output_1.png)

### content.php

This is the bare minimum file that is the common fallback for all of the triggers.

This output will be contained in a wrapper theme file by EasySocial that automatically renders the title, description and the privacy (accordingly to the field configuration parameters). As such, this file does not have full control over the field block and you will only need to code the essential part of the fields.

### event_content.php

This is the same as content.php where the output is contained within a wrapper theme file. The only difference is this is specific to an event, and will only render according to which event name.

### event.php

This is the full block of the rendered field area. You will get full control over the whole field area, but the default set of output will not be rendered, and you will have to code it yourself.

This is useful if your field does not requires title or description, or would like have full area to display something.