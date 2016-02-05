
# GENERIC
Low-specificity, far-reaching rulesets (e.g. resets, normalise.css, box-sizing).

## generic.reset
Basic reset to complement normalize.css.

<https://github.com/inuitcss/generic.reset>
```
@import inuit-normalize/generic.reset
```
```
$ bower install --save inuit-reset
$ npm install --save inuit-reset
```

## generic.normalize
@necolas’ normalize.css (https://github.com/necolas/normalize.css/).

<https://github.com/inuitcss/generic.normalize>
```
@import inuit-normalize/generic.normalize
```
```
$ bower install --save inuit-normalize
$ npm install --save inuit-reset
```
### Comments
> This is an exact clone of normalize.css

## generic.box-sizing
Global box-sizing options.

<https://github.com/inuitcss/generic.box-sizing>
```
@import inuit-box-sizing/generic.box-sizing
```
```
$ bower install --save inuit-box-sizing
$ npm install --save inuit-box-sizing
```
### Comments
> Including this will set the global `box-sizing` state to `border-box`.

## generic.shared
High-level styling across shared rulesets.

<https://github.com/inuitcss/generic.shared>
```
@import inuit-shared/generic.shared
```
```
$ bower install --save inuit-shared
$ npm install --save inuit-shared
```
### Comments
<https://github.com/inuitcss/generic.shared/blob/master/_generic.shared.scss>
> Will create a vertical rhythm by applying a consistent margin-bottom to
> h1, h2, h3, h4, h5, h6, ul, ol, dl, blockquote, p, address, hr, table, fieldset, figure, pre and %margin-bottom

> Left indents ul, ol, dd, %margin-left by a consistent amount.

---
