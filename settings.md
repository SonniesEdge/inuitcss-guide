# SETTINGS
Global variables, site-wide settings, config switches, etc.

## settings.defaults
InuitCSS’ default settings.

<https://github.com/inuitcss/settings.defaults>

```
@import inuit-defaults/settings.defaults
```
```
$ bower install --save inuit-defaults
$ npm install --save inuit-defaults
```
### Extracted notes
<https://github.com/inuitcss/settings.defaults/blob/master/_settings.defaults.scss>
```
// These variables are inuitcss’ defaults; they should not be modified or
// adjusted directly; you should predefine the variables in your own project.
```
### Comments
> Like the above says, never alter these directly, but create your own settings file to override them from.


## settings.responsive
Define our initial breakpoint aliases and conditions.

<https://github.com/inuitcss/settings.responsive>
```
@import inuit-responsive-settings/settings.responsive
```
```
$ bower install --save inuit-responsive-settings
$ npm install --save inuit-responsive-settings
```
### Extracted notes
<https://github.com/inuitcss/settings.responsive/blob/master/_settings.responsive.scss>
```
$breakpoints: (
    "palm"          "screen and (max-width: 44.9375em)",
    "lap"           "screen and (min-width: 45em) and (max-width: 63.9375em)",
    "lap-and-up"    "screen and (min-width: 45em)",
    "portable"      "screen and (max-width: 63.9375em)",
    "desk"          "screen and (min-width: 64em)",
    "retina"        "(-webkit-min-device-pixel-ratio: 2), (min-resolution: 192dpi), (min-resolution: 2dppx)"
) !default;
```
### Comments
> These are default breakpoints. $breakpoints can be overridden later.
