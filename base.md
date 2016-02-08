# BASE
Unclassed HTML elements (Directly selects element types e.g. a {}, blockquote {}, address {}).

## base.page
Base page-level styling.

<https://github.com/inuitcss/base.page>
```
@import inuit-page/base.page
```
```
$ bower install --save inuit-page
$ npm install --save inuit-page
```
### Extracted notes
<https://github.com/inuitcss/base.page/blob/master/_base.page.scss>
```
* High-, page-level styling.
*
* 1. Set the default `font-size` and `line-height` for the entire project,
*    sourced from our default variables. The `font-size` is calculated to exist
*    in ems, the `line-height` is calculated to exist unitlessly.
* 2. Force scrollbars to always be visible to prevent awkward ‘jumps’ when
*    navigating between pages that do/do not have enough content to produce
*    scrollbars naturally.
* 3. Ensure the page always fills at least the entire height of the viewport.
* 4. Prevent certain mobile browsers from automatically zooming fonts.
* 5. Fonts on OSX will look more consistent with other systems that do not
*    render text using sub-pixel anti-aliasing.
```

## base.headings
Base-level heading styles.

<https://github.com/inuitcss/base.headings>
```
@import inuit-headings/base.headings
```
```
$ bower install --save inuit-headings
$ npm install --save inuit-headings
```
### Extracted notes
<https://github.com/inuitcss/base.headings/blob/master/_base.headings.scss>
```
// Heading sizes are defined in variables
// $inuit-heading-size-1:  36px !default;
// $inuit-heading-size-2:  30px !default;
// $inuit-heading-size-3:  24px !default;
// $inuit-heading-size-4:  20px !default;
// $inuit-heading-size-5:  16px !default;
// $inuit-heading-size-6:  14px !default;
```

## base.images
Simple image styles.

<https://github.com/inuitcss/base.images>
```
@import inuit-images/base.images
```
```
$ bower install --save inuit-images
$ npm install --save inuit-images
```

## base.paragraphs
Simple paragraph styles.

<https://github.com/inuitcss/base.paragraphs>
```
@import inuit-images/base.paragraphs
```
```
$ bower install --save inuit-paragraphs
$ npm install --save inuit-paragraphs
```
### Extracted notes
<https://github.com/inuitcss/base.paragraphs/blob/master/_base.paragraphs.scss>
```
// Provides the .lede class.
// The .lede class is used to make the introductory text (usually a paragraph)
```

## base.lists
Simple list styles.

<https://github.com/inuitcss/base.lists>
```
@import inuit-images/base.lists
```
```
$ bower install --save inuit-lists
$ npm install --save inuit-lists
```
```
// Remove extra vertical spacing when nesting lists.
```

---
