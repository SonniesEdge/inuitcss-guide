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

InuitCSS isn't like Bootstrap or Zurb Foundation. It won't give you an out-of-the-box layout, or nicely styled buttons. It's a bunch of helper functions, written in Sass, that will help you to build your own systems. 

## Installing
You can get an initial install of InuitCSS going with:

`bower install --save-dev inuit-starter-kit`

It'll install some basics and let you start playing. 




## Modules
InuitCSS is *increadibly* modular and has all documentation inline. While this means that you only ever pull in what you need, and there's information inline, it means that getting a  high-level overviews is frustrating.

Soooo, here's an attempt at building one!

The following list breaks things up according to the inverted triangle philosophy, but notice that each module is prefixed with something like `inuit-defaults`. This helps group things by what they *do*. Then inside each group is the triangle stack level, e.g. `settings.defaults`, detailing *where* it affects. 

I've included a simple @import example, along with the bower install command and a link to the documentation. I found that's what I needed most when starting out!

### Settings
Global variables, site-wide settings, config switches, etc.

#### settings.defaults
InuitCSS’ default settings
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

### Tools
```
// @import inuit-functions/tools.functions
//      inuitcss’ default functions
//      bower install --save inuit-functions
//      https://github.com/inuitcss/tools.functions
```

```
// @import inuit-mixins/tools.mixins
//      inuitcss’ default mixins
//      bower install --save inuit-mixins
//      https://github.com/inuitcss/tools.mixins
```

```
// @import inuit-responsive-tools/tools.responsive
//      Currently, this inuitcss module just sets up our media query mixin.
//      bower install --save inuit-responsive-tools
//      https://github.com/inuitcss/tools.responsive
```

```
// @import inuit-tools-widths/tools.widths
//      inuitcss width classes generator
//      bower install --save inuit-tools-widths
//      https://github.com/inuitcss/tools.widths
```




### Generic
```
// @import inuit-normalize/generic.reset
//      Basic reset to complement normalize.css.
//      bower install --save inuit-reset
//      https://github.com/inuitcss/generic.reset
```

```
// @import inuit-normalize/generic.normalize
//      @necolas’ normalize.css.
//      bower install --save inuit-normalize
//      https://github.com/inuitcss/generic.normalize
```

```
// @import inuit-box-sizing/generic.box-sizing
//      Global box-sizing options.
//      bower install --save inuit-box-sizing
//      https://github.com/inuitcss/generic.box-sizing
```

```
// @import inuit-shared/generic.shared
//      High-level styling across shared rulesets
//      bower install --save inuit-shared
//      https://github.com/inuitcss/generic.shared
```

### Base
```
// @import inuit-page/base.page
//      Base page-level styling.
//      bower install --save inuit-page
//      https://github.com/inuitcss/base.page
```

```
// @import inuit-headings/base.headings
//      Base-level heading styles.
//      bower install --save inuit-headings
//      https://github.com/inuitcss/base.headings
```

```
// @import inuit-images/base.images
//      Simple image styles
//      bower install --save inuit-images
//      https://github.com/inuitcss/base.images

// @import inuit-images/base.paragraphs
//      Simple paragraph styles
//      bower install --save inuit-paragraphs
//      https://github.com/inuitcss/base.paragraphs
```

```
// @import inuit-images/base.lists
//      Simple list styles
//      bower install --save inuit-lists
//      https://github.com/inuitcss/base.lists
```

### Objects
```
// @import inuit-buttons/objects.buttons
//      Simple, extensible button objects
//      bower install --save inuit-buttons
//      https://github.com/inuitcss/objects.buttons
```

```
// @import inuit-tables/objects.tables
//      Basic table styles.
//      bower install --save inuit-tables
//      https://github.com/inuitcss/objects.tables
```

```
// @import inuit-pack/objects.pack
//      Cause items to pack up to automatically fill their parent.
//      bower install --save inuit-pack
//      https://github.com/inuitcss/objects.pack
```

```
// @import inuit-media/objects.media
//      @stubbornella’s media object
//      bower install --save inuit-media
//      https://github.com/inuitcss/objects.media
```

```
// @import inuit-tabs/objects.tabs
//      Simple tabs abstraction.
//      bower install --save inuit-tabs
//      https://github.com/inuitcss/objects.tabs
```

```
// @import inuit-flag/objects.flag
//      The flag object
//      bower install --save inuit-flag
//      https://github.com/inuitcss/objects.flag
```

```
// @import inuit-box/objects.box
//      Simple object to make boxed-off content.
//      bower install --save inuit-box
//      https://github.com/inuitcss/objects.box
```

```
// @import inuit-list-block/objects.list-block
//      A simple, blocky list object.
//      bower install --save inuit-list-block
//      https://github.com/inuitcss/objects.list-block
```

```
// @import inuit-list-ui/objects.list-ui
//      A simple, keyline-delimited blocky list object.
//      bower install --save inuit-list-ui
//      https://github.com/inuitcss/objects.list-ui
```

```
// @import inuit-list-inline/objects.list-inline
//      Display a list as one horizontal row.
//      bower install --save inuit-list-inline
//      https://github.com/inuitcss/objects.list-inline
```

```
// @import inuit-block/objects.block
//      Stack an image above some text content.
//      bower install --save inuit-block
//      https://github.com/inuitcss/objects.block
```

```
// @import inuit-layout/objects.layout
//      inuitcss’ answer to the traditional grid system
//      bower install --save inuit-layout
//      https://github.com/inuitcss/objects.layout
```

```
// @import inuit-list-bare/objects.list-bare
//      A simple object to remove bullets and indents from lists
//      bower install --save inuit-list-bare
//      https://github.com/inuitcss/objects.list-bare
```

### Components

InuitCSS deliberately doesn't provide any components, so this is where your own code should come in! Define your page components here, utilising the support provided by those rules higher up the stack.

```
@import your/components/here
```

### Trumps
```
// @import inuit-widths-responsive/trumps.widths-responsive
//      bower install --save inuit-widths-responsive
//      https://github.com/inuitcss/trumps.widths-responsive
```

```
// @import inuit-spacing-responsive/trumps.spacing-responsive
//      bower install --save inuit-spacing-responsive
//      https://github.com/inuitcss/trumps.spacing-responsive
```

```
// @import inuit-spacing/trumps.spacing
//      Spacing helper classes
//      bower install --save inuit-spacing
//      https://github.com/inuitcss/trumps.spacing
```

```
// @import inuit-clearfix/trumps.clearfix
//      Simple clearfix helper
//      bower install --save inuit-clearfix
//      https://github.com/inuitcss/trumps.clearfix
```

```
// @import inuit-headings-trumps/trumps.headings
//      Class-bassed equivalents of our regular h1–6 rules
//      bower install --save inuit-headings-trumps
//      https://github.com/inuitcss/trumps.headings
```

```
// @import inuit-print/trumps.print
//      Very crude, very basic reset-like module for print styles
//      bower install --save inuit-print
//      https://github.com/inuitcss/trumps.print
```

```
// @import inuit-widths/trumps.widths
//      Helper classes to drop widths onto elements such as grid systems
//      bower install --save inuit-widths
//      https://github.com/inuitcss/trumps.widths
```
