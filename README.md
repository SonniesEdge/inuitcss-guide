# The helpless developer's guide to InuitCSS
Demystifying the InuitCSS experience.

[The official guide](https://github.com/inuitcss/getting-started) doesn't really cut it when it comes to explaining how to use the latest, ultra-modular version of [InuitCSS](https://github.com/inuitcss). Here's something that hopefully makes things a bit easier to understand.

## Philosophy
InuitCSS is based on the Inverted Triangle philiosphy of CSS inheritence, an attempt to express best practice in large-scale web projects. The rules at the top should be extremely generic, while those at the bottom should be ultra-specific overrides.

![](stack.png)

* **Settings:** Global variables, site-wide settings, config switches, etc.
* **Tools:** Site-wide mixins and functions.
* **Generic:** Low-specificity, far-reaching rulesets (e.g. resets, normalise.css, box-sizing).
* **Base:** Unclassed HTML elements (Directly selects element typs e.g. a {}, blockquote {}, address {}).
* **Objects:** Objects, abstractions, and design patterns (e.g. .media {}). Cosmetic-free.
* **Components:** Discrete, complete chunks of UI (e.g. .carousel {}). Cosmetically-designed components. This is the one layer that inuitcss doesn’t get involved with.
* **Trumps:** High-specificity, very explicit selectors. Overrides and helper classes (e.g. .hidden {}).


These links might shed some light on the whole thing:
* <http://csswizardry.net/talks/2014/11/itcss-dafed.pdf> - comes up on Google when you search for "ITCSS".
* <http://www.creativebloq.com/web-design/manage-large-scale-web-projects-new-css-architecture-itcss-41514731> - Interview with Harry Roberts on ITCSS


## Practical

InuitCSS isn't like Bootstrap or Zurb Foundation. It won't give you an out-of-the-box layout, or nicely styled buttons. It's a bunch of helper functions, mixins and classes, written in Sass, that will help you to build your own systems.

## Installing
You can get an initial install of InuitCSS going with:

`bower install --save-dev inuit-starter-kit`

It'll install some basics and let you start playing.




## Modules
InuitCSS is *increadibly* modular and has all documentation inline. While this means that you only ever pull in what you need, and there's information inline, it means that getting a  high-level overview is extremely frustrating. This guide attempts to address that.

The following list breaks things up according to the inverted triangle philosophy, but notice that each module is prefixed with something like `inuit-defaults`. This is a bower or npm package name. A bower or npm package might contain more than one module. Then after the '/' in each group is the triangle stack level, e.g. `settings.xxxxxx`, detailing *where* in the triangle it affects, and, after the '.', the effect name `nnnnnn.default`, describing what it *does*.

So, `inuit-tools-widths/tools.widths` belongs to the `inuit-tools-widths` package, affects the `tools` layer of the triangle and provides `widths` functionality.

Meanwhile, `inuit-page/base.page` belongs to the `inuit-page` package, affects the `base` layer and provides functionality that deals with a `page`.

I've included a simple @import example, along with the bower install command and a link to the documentation. I found that's what I needed most when starting out!

### SETTINGS
Global variables, site-wide settings, config switches, etc.

#### settings.defaults
InuitCSS’ default settings.

<https://github.com/inuitcss/settings.defaults>

```
@import inuit-defaults/settings.defaults
```
```
bower install --save inuit-defaults
```

#### settings.responsive
Define our initial breakpoint aliases and conditions.

<https://github.com/inuitcss/settings.responsive>
```
@import inuit-responsive-settings/settings.responsive
```
```
bower install --save inuit-responsive-settings
```

---

### TOOLS
Site-wide mixins and functions.

#### tools.functions
*REQUIRED:* The inuitcss functions module—like mixins—contains a few framework functions that are required for using any of the rest of inuitcss.
<https://github.com/inuitcss/tools.functions>
```
@import inuit-functions/tools.functions
```
```
$ bower install --save inuit-functions
$ npm install --save inuit-functions
```
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

#### tools.mixins
*REQUIRED:* inuitcss’ default mixins.
<https://github.com/inuitcss/tools.mixins>
```
@import inuit-mixins/tools.mixins
```
```
bower install --save inuit-mixins
```
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

#### tools.responsive
Sets up our media query mixin.

<https://github.com/inuitcss/tools.responsive>
```
@import inuit-responsive-tools/tools.responsive
```
```    
bower install --save inuit-responsive-tools     
```
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

#### tools.widths
inuitcss width classes generator.

<https://github.com/inuitcss/tools.widths>
```
@import inuit-tools-widths/tools.widths
```
```
bower install --save inuit-tools-widths
```
<https://github.com/inuitcss/tools.widths/blob/master/_tools.widths.scss>
```
// A mixin to spit out our width classes. Pass in the columns we want the widths
// to have, and an optional suffix for responsive widths. E.g. to create thirds
// and quarters for a small breakpoint:
//
// @include inuit-widths(3 4, -sm);
```
> This generates only widths! This is NOT a grid solution!


---


### GENERIC
Low-specificity, far-reaching rulesets (e.g. resets, normalise.css, box-sizing).

#### generic.reset
Basic reset to complement normalize.css.

<https://github.com/inuitcss/generic.reset>
```
@import inuit-normalize/generic.reset
```
```
bower install --save inuit-reset
```

#### generic.normalize
@necolas’ normalize.css (https://github.com/necolas/normalize.css/).

<https://github.com/inuitcss/generic.normalize>
```
@import inuit-normalize/generic.normalize
```
```
bower install --save inuit-normalize
```

#### generic.box-sizing
Global box-sizing options.

<https://github.com/inuitcss/generic.box-sizing>
```
@import inuit-box-sizing/generic.box-sizing
```
```
bower install --save inuit-box-sizing
```

#### generic.shared
High-level styling across shared rulesets.

<https://github.com/inuitcss/generic.shared>
```
@import inuit-shared/generic.shared
```
```
bower install --save inuit-shared
```

---

### BASE
Unclassed HTML elements (Directly selects element types e.g. a {}, blockquote {}, address {}).

#### base.page
Base page-level styling.

<https://github.com/inuitcss/base.page>
```
@import inuit-page/base.page
```
```
bower install --save inuit-page
```

#### base.headings
Base-level heading styles.

<https://github.com/inuitcss/base.headings>
```
@import inuit-headings/base.headings
```
```
bower install --save inuit-headings
```

#### base.images
Simple image styles.

<https://github.com/inuitcss/base.images>
```
@import inuit-images/base.images
```
```
bower install --save inuit-images
```

#### base.paragraphs
Simple paragraph styles.

<https://github.com/inuitcss/base.paragraphs>
```
@import inuit-images/base.paragraphs
```
```
bower install --save inuit-paragraphs
```

#### base.lists
Simple list styles.

<https://github.com/inuitcss/base.lists>
```
@import inuit-images/base.lists
```
```
bower install --save inuit-lists
```

---

### OBJECTS
Cosmetic-free objects, abstractions, and design patterns (e.g. .media {})

####  objects.buttons
Simple, extensible button objects.

<https://github.com/inuitcss/objects.buttons>
```
@import inuit-buttons/objects.buttons
```
```
bower install --save inuit-buttons
```

#### objects.tables
Basic table styles.

<https://github.com/inuitcss/objects.tables>
```
@import inuit-tables/objects.tables
```
```
bower install --save inuit-tables
```

#### objects.pack
Cause items to pack up to automatically fill their parent.

<https://github.com/inuitcss/objects.pack>
```
@import inuit-pack/objects.pack
```
```
bower install --save inuit-pack
```

#### objects.media
@stubbornella’s media object (<http://www.stubbornella.org/content/2010/06/25/the-media-object-saves-hundreds-of-lines-of-code/>).

<https://github.com/inuitcss/objects.media>
```
@import inuit-media/objects.media
```
```
bower install --save inuit-media
```

#### objects.tabs
Simple tabs abstraction.

<https://github.com/inuitcss/objects.tabs>
```
@import inuit-tabs/objects.tabs
```
```
bower install --save inuit-tabs
```

#### objects.flag
The flag object (<http://csswizardry.com/2013/05/the-flag-object>).

<https://github.com/inuitcss/objects.flag>
```
@import inuit-flag/objects.flag
```
```
bower install --save inuit-flag
```

#### objects.box
Simple object to make boxed-off content.

<https://github.com/inuitcss/objects.box>
```
@import inuit-box/objects.box
```
```
bower install --save inuit-box
```

#### objects.list-block
A simple, blocky list object.

<https://github.com/inuitcss/objects.list-block>
```
@import inuit-list-block/objects.list-block
```
```
bower install --save inuit-list-block
```

#### objects.list-ui
A simple, keyline-delimited blocky list object.

https://github.com/inuitcss/objects.list-ui
```
@import inuit-list-ui/objects.list-ui
```
```
bower install --save inuit-list-ui
```

#### objects.list-inline
Display a list as one horizontal row.

<https://github.com/inuitcss/objects.list-inline>
```
@import inuit-list-inline/objects.list-inline
```
```
bower install --save inuit-list-inline
```

#### objects.block
Stack an image above some text content.

<https://github.com/inuitcss/objects.block>
```
@import inuit-block/objects.block
```
```
bower install --save inuit-block
```

#### objects.layout
inuitcss’ answer to the traditional grid system.

<https://github.com/inuitcss/objects.layout>
```
@import inuit-layout/objects.layout
```
```
bower install --save inuit-layout
```

#### objects.list-bare
A simple object to remove bullets and indents from lists.

<https://github.com/inuitcss/objects.list-bare>
```
@import inuit-list-bare/objects.list-bare
```
```
bower install --save inuit-list-bare
```

---

### COMPONENTS

InuitCSS deliberately doesn't provide any visual components, so this is where your own code should come in! Define your page components here, utilising the support provided by those rules higher up the stack.

```
@import your/components/here
```

---

### TRUMPS
High-specificity, very explicit selectors. Overrides and helper classes (e.g. .hidden {}).

#### trumps.widths-responsive
No description.

<https://github.com/inuitcss/trumps.widths-responsive>
```
@import inuit-widths-responsive/trumps.widths-responsive
```
```
bower install --save inuit-widths-responsive
```

#### trumps.spacing-responsive
No description.

<https://github.com/inuitcss/trumps.spacing-responsive>
```
@import inuit-spacing-responsive/trumps.spacing-responsive
```
```
bower install --save inuit-spacing-responsive
```

#### trumps.spacing
Spacing helper classes.

<https://github.com/inuitcss/trumps.spacing>
```
@import inuit-spacing/trumps.spacing
```
```
bower install --save inuit-spacing
```

#### trumps.clearfix
Simple clearfix helper.

<https://github.com/inuitcss/trumps.clearfix>
```
@import inuit-clearfix/trumps.clearfix
```
```
bower install --save inuit-clearfix
```

#### trumps.headings
Class-bassed equivalents of our regular h1–6 rules.

<https://github.com/inuitcss/trumps.headings>
```
@import inuit-headings-trumps/trumps.headings
```
```
bower install --save inuit-headings-trumps
```


#### trumps.print
Very crude, very basic reset-like module for print styles.

<https://github.com/inuitcss/trumps.print>
```
@import inuit-print/trumps.print
```
```
bower install --save inuit-print
```

#### trumps.widths
Helper classes to drop widths onto elements such as grid systems.

<https://github.com/inuitcss/trumps.widths>
```
@import inuit-widths/trumps.widths
```
```
bower install --save inuit-widths
```
