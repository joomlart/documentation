There are 4 types of stylesheets:

* Global stylesheets
* Component stylesheets
* Theme stylesheets
* User-configured stylesheets

Global stylesheets
------------------

Global stylesheets are located in `/media/foundry/4.0/styles`.

The purpose of global stylesheets is to provide _shared stylesheets that is used by all components_. It contains stylesheets that accompanies the script counterpart. For example, if you use **dialog**, your theme stylesheet should import dialog's stylesheet at and add your own further modifications, e.g.

```
@import "dialog";

// Dialog customization specifically for my theme
.dialog-close-button {
    background: red;
}
```

Component stylesheets
---------------------

Component stylesheets are located in `/media/com_component/styles`.

The purpose of component stylesheets is to provide _shared stylesheets that is used by both site and admin theme stylesheets_.

Component stylesheets contain:

* Configuration stylesheet.
* Main component stylesheet.
* Additional stylesheets.

**Configuration stylesheet**

Configuration stylesheet is located in `/media/com_component/styles/config.less`. It contains mixins & variables that is used to compile component & theme stylesheets. It **MUST** at least contain a `@ComponentName` variable:

```
@ComponentName: "#cp_";
```

**Main component stylesheet**

Main component stylesheet is located in `/media/com_component/styles/component.less`. This file must import the `config` file and ideally should follow the following format:

```
@import "config";

(~"@{ComponentName}") {
    /* Stylesheet here */
}
```

**Additional stylesheets**

Additional stylesheets are non-essential stylesheets that can be imported only when they are required.

Theme stylesheets
-----------------

Theme stylesheets are located in `/components/com_component/themes/theme_name` for site themes and `/administrator/components/com_component/themes/theme_name` for admin themes.

Component stylesheets contain:

* Main stylesheet.
* Section stylesheet

#### Main stylesheet
- style.json - **Manifest**
- style.css - **Compiled stylesheet**
- style.default.css - **Default fallback stylesheet**
- style.xml - **UI Configuration file (1.3+)**
- style.cache - **Cache file**
- style.less - **No longer used. Replaced by manifest.**

#### Section stylesheet
- photos.less - **Section stylesheet**
- photos.css - **Compiled stylesheet**
- photos.default.css - **Default fallback stylesheet**
- photos.xml -- **UI Configuration file (1.3+)**
- photos.cache -- **Cache file**
- photos\variables.less -- **Section variables**
- photos\item.less -- **Child stylesheet**
- photos\item.php -- **Child stylesheet generator (1.3+)**

Every section stylesheet, e.g. `photos.less` **MUST import configuration file** at the very beginning of the stylesheet. It should also contain **ONLY import directives**, e.g.

```
@import "config"
@import "photos/variables"
@import "photos/item"
@import "photos/browser"
```

User-configured stylesheets (1.3+)
----------------------------------

User-configured stylesheets are located in `/media/com_component/themes/site/theme_name` for site themes and `/media/com_component/themes/admin/theme_name` for admin themes.

The purpose of user-configured stylesheet is to provide a place for users to add their own custom configurations to the theme stylesheet.

User-configured stylesheets are the placed highest in the import ordering seeking order and the stylesheet files here are generated from the backend theme configuration page.