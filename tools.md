
# TOOLS
Site-wide mixins and functions.

## tools.functions
*REQUIRED:* The inuitcss functions module—like mixins—contains a few framework functions that are required for using any of the rest of inuitcss.
<https://github.com/inuitcss/tools.functions>
```
@import inuit-functions/tools.functions
```
```
$ bower install --save inuit-functions
$ npm install --save inuit-functions
```
### Extracted notes
<https://github.com/inuitcss/tools.functions/blob/master/_tools.functions.scss>
```
// Maths helpers.
//
// Halve and double numbers, returning rounded integers. E.g.:
//
// .foo {
//     padding: halve(3.2px);
// }
```

## tools.mixins
*REQUIRED:* inuitcss’ default mixins.
<https://github.com/inuitcss/tools.mixins>
```
@import inuit-mixins/tools.mixins
```
```
$ bower install --save inuit-mixins
$ npm install --save inuit-mixins
```
### Extracted notes
<https://github.com/inuitcss/tools.mixins/blob/master/_tools.mixins.scss>
```
// Create a fully formed type style (sizing and vertical rhythm) by passing in a
// single value, e.g.:
//
// .foo {
//     @include inuit-font-size(12px);
// }
//
// This will generate a rem-based font-size with its pixel fallback, as well as
// a unitless line-height which will place the element on your baseline, e.g.:
//
// .foo {
//     font-size: 12px;
//     font-size: 0.75rem;
//     line-height: 2;
// }
```

## tools.responsive
Sets up our media query mixin.

<https://github.com/inuitcss/tools.responsive>
```
@import inuit-responsive-tools/tools.responsive
```
```    
$ bower install --save inuit-responsive-tools
$ npm install --save inuit-responsive-tools
```
### Extracted notes
<https://github.com/inuitcss/tools.responsive/blob/master/_tools.responsive.scss>
```
// A simple mixin to quickly generate whole media queries from the aliases and
// conditions defined in `_settings.responsive.scss`.
//
// Usage:
//
// .foo {
//     color: green;
//
//     @include media-query(palm) {
//         color: red;
//     }
//
// }
```

## tools.widths
inuitcss width classes generator.

<https://github.com/inuitcss/tools.widths>
```
@import inuit-tools-widths/tools.widths
```
```
$ bower install --save inuit-tools-widths
$ npm install --save inuit-tools-widths
```
### Extracted notes
<https://github.com/inuitcss/tools.widths/blob/master/_tools.widths.scss>
```
// A mixin to spit out our width classes. Pass in the columns we want the widths
// to have, and an optional suffix for responsive widths. E.g. to create thirds
// and quarters for a small breakpoint:
//
// @include inuit-widths(3 4, -sm);
```
### Comments
> This generates only widths! This is NOT a grid solution!


---
