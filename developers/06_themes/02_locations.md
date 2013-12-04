<table>
<thead>
    <td><strong>Location</strong></td>
    <td><strong>Absolute</strong><br/>use with @import</td>
    <td><strong>Relative</strong><br/>use with url()</td>
    <td><strong>Path</strong></td>
</thead>
<tr>
    <td>Site current theme</td>
    <td>@{site_uri}</td>
    <td>@{site}</td>
    <td>/components/<u>com_component</u>/themes/<u>current_theme</u></td>
</tr>
<tr>
    <td>Site base theme</td>
    <td>@{site_base}</td>
    <td>@{site_base_uri}</td>
    <td>/components/<u>com_component</u>/themes/<u>base_theme</u></td>
</tr>
<tr>
    <td>Admin current theme</td>
    <td>@{admin}</td>
    <td>@{admin_uri}</td>
    <td>/administrator/components/<u>com_component</u>/themes/<u>current_theme</u></td>
</tr>
<tr>
    <td>Admin base theme</td>
    <td>@{admin_base}</td>
    <td>@{admin_base_uri}</td>
    <td>/administrator/components/<u>com_component</u>/themes/<u>base_theme</u></td>
</tr>
<tr>
    <td>Component media folder</td>
    <td>@{media}</td>
    <td>@{media_uri}</td>
    <td>/media/<u>com_component</u></td>
</tr>
<tr>
    <td>Component shared stylesheets</td>
    <td>@{component}</td>
    <td>@{component_uri}</td>
    <td>/media/<u>com_component</u>/styles</td>
</tr>
<tr>
    <td>Foundry</td>
    <td>@{foundry}</td>
    <td>@{foundry_uri}</td>
    <td>/media/foundry/4.0</td>
</tr>
<tr>
    <td>Global stylesheets</td>
    <td>@{global}</td>
    <td>@{global_uri}</td>
    <td>/media/foundry/4.0/styles</td>
</tr>
</table>

Import ordering
---------------
Foundry stylesheets is built on top of LESS framework with Joomla's template override system in mind.
When importing external stylesheets using `@import`, the less compiler will look for the stylesheet file based on the following order of asset locations:

1. site-override / admin-override
2. site / admin
3. site-base / admin-base
4. media
5. foundry

Path relativity
---------------
The relative path of all your stylesheet files, wherever they are located, is always the path of your current template stylesheet folder `@{theme}\styles`. This is because the compiled stylesheet file is created at this location `@{theme}\styles\style.css`.

Therefore, if you are adding a stylesheet under the theme override `${theme-override}` folder or any other locations that is not your current theme folder, all external asset linking like `url()` should contain the path variable prefix, e.g.
```
background: url('@{theme-override}/images/image.png');
background: url('@{media}/images/image.png');
background: url('@{foundry}/styles/bootstrap/images/image.png');
```

#### Important!
For your base theme, **YOU MUST** add the path variable prefix in front because the stylesheet may be loaded from another theme, e.g.
```
background: url('@{theme-base}/images/image.png');
```

Importing absolute path
-----------------------
The less compiler used in Foundry has been modified to import absolute paths. To tell the compiler that you are providing an absolute path, add a percent symbol prefix, e.g.
```css
@import "%/home/user/public_html/style.less";
@import "@{__theme-base}/style"; /* When using one of the preset locations */
