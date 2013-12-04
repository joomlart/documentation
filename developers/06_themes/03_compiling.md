The main stylesheet `@{theme}/styles/style.less` is sent to the php less compiler and outputs to `@{theme}/styles/style.css`.

### Cache file
The compiler also creates a cache file `@{theme}/styles/style.cache` which is a serialized php object that contains:
* File modification date the main stylesheet.
* File modification date of all imported external stylesheets.

### Fallback
When compiling fails, it will attempt to load the last compiled stylesheet `@{theme}/styles/style.css`. If the last compiled stylesheet does not exist, it will revert to the failsafe stylesheet `@{theme}/styles/style.failsafe.css`. Failsafe stylesheet is the pre-compiled stock stylesheet the came bundled with the component package.

### Compile behaviour
Under the component's `configuration.ini` file, there should be a setting to determines how and when theme stylesheets are compiled.
```
layout_compile_stylesheet = auto | cache | force | manual
```
<table>
<tr>
<td><strong>auto</strong></td>
<td>Uses <strong>manual</strong> during production mode. Uses <strong>cache</strong> during development mode.</td>
</tr>
<tr>
<td><strong>cache</strong></td>
<td>Compiles whenever there are new changes within the stylesheet files. If compile fails, load failsafe stylesheet.</td>
</tr>
<tr>
<td><strong>force</strong></td>
<td>Compiles on every page load. If compile fails, load failsafe stylesheet.</td>
</tr>
<tr>
<td><strong>manual</strong></td>
<td>Loads last compiled stylesheet. If last compiled stylesheet is not found, load failsafe stylesheet.</td>
</tr>
</table>

### Backend configuration switch
* When switching to "cache/force" compile, it should attempt to recompile the stylesheet using 2 separate ajax request FIRST, one for frontend, one for backend.
* If both request are successful, then ONLY switch to the "cache/force" compile mode.
* If there's an error in one of those ajax request, then PREVENT them from switching.
* Also offer a button to manually recompile using the same 2 ajax request method.
* The reason why it needs to be done this way is to ensure user doesn't switch to one mode and after saving the configuration page, everything white-out.

```