# ACSS - BEM - OOCSS - SMACSS (template)

![alt text](https://img.shields.io/badge/build-passing-brightgreen.svg "Build passing")
![alt text](https://img.shields.io/badge/license-CCO-blue.svg "CCO 1.0")

> Atomic CSS (ACSS)

> Block, Element, Modifier (BEM)

> Object Oriented CSS (OOCSS)

> Scalable Modular Architecture CSS (SMACSS)

### This repository has some folder and file structure for you:

Inside in this sample:

- [LESS Mixins](https://github.com/prod3v3loper/LESS-Mixins)
- [CSS Grid](https://github.com/prod3v3loper/CSS-Grid)

```less
less/
|- _base/
|  |- _default.less
|  |- _config.less
|  |- _mixin.less
|  |- ... add more ...
|
|- _layout/
|  |- _l-default.less
|  |- _l-float.less
|  |- _l-margin.less
|  |- _l-grid.less
|  |- ... add more ...
|
|- _module/
|  |- _m-default.less
|  |- _m-button.less
|  |- ... add more ...
|
|- _state/
|  |- _s-default.less
|  |- ... add more ...
|
|- _theme/
|  |- _t-default.less
|  |- ... add more ...
|
|- application/
|  |- style.less
 
css/
|- style.css
```

###### _base

[_config.less](less/_base/_config.less)

[_default.less](less/_base/_default.less)

_mixin.less [(less-mixins)](https://github.com/prod3v3loper/less-mixins/)

###### _layout

[_l-default.less](less/_layout/_l-default.less)

[_l-float.less](less/_layout/_l-float.less)

[_l-margin.less](less/_layout/_l-margin.less)

_l-grid.less [(css-grids)](https://github.com/prod3v3loper/css-grids/)

###### _module

[_m-default.less](less/_module/_m-default.less)

[_m-button.less](less/_module/_m-button.less)

###### _state

[_s-default.less](less/_state/_s-default.less)

###### _theme

[_t-default.less](less/_theme/_t-default.less)

## Usage

### General Usage

In general you should include the folder `less/` in `build` into your 
project folder structur and create your own ACSS BEM SMACSS OOCSS work as suggested in the docs for each ACSS BEM SMACSS OOCSS template.

### ACSS

> Atomic CSS

```css
.mt-20 {
    margin-top: 20px;
}

/* Or */

.fl {
    float: left;
}
```

```html
<article class="mt-20">
    <img src="" alt="" title="" class="fl">
</article>
```

### BEM

> Block, Element, Modifier

```css
/* This is the Block */
.block1 {}
.block2 {}

/* This is an element, that helps to form the block as a whole */
.block1__element1 {}
.block2__element2 {}

/* This modifies the element or a block*/
.block1--modifier1 {}
.block2--modifier2 {}
```

```html
<header class="block1">
    <h1 class="block1__element1">
        <a class="block1--modifier1" href="https://www.tnado.com/">tnado SEO CMS</a>
    </h1>
</header>
<article class="block2">
    <h1 class="block2__element2 block2--modifier2">tnado SEO CMS</h1>
</article>
```
### OOCSS

> Separation of Structure From Skin

Here an ID was used and to which the skin was still defined

This is not good readable and not good scaleable (PURE CSS):
```css
/* No id but we have more buttons on the site */
#button {

    width: 200px;
    height: 50px;
    padding: 10px;
    border: solid 1px #ccc;
    background: linear-gradient(#ccc, #222);
    box-shadow: rgba(#000000,.5) 2px 2px 5px;
}
```

Good, you do this with preprocessors e.g. [LESS](http://lesscss.org/):
```less
LESS - OOCSS, BEM and ACSS
/* Give the button defaults */
.button {

    width: 200px;
    height: 50px;

    /* You can give here the padding but you need it not once */
    /* &__element {
        padding: 10px;
    } */

    /* Give the button the modifier */
    &--skin {

        border: solid 1px #ccc;
        background: linear-gradient(#ccc, #222);
        box-shadow: rgba(#000000,.5) 2px 2px 5px;
    }
}

/* Give a helper padding (ACSS) from helper file */
.p-10 {
    padding: 10px;
}
```

```html
<button class="button button__skin p-10">Send</button>
```

### SMACSS

> Scalable and Modular Architecture for CSS

Not good to use the elements directly `nav > li` 

Augmented CSS:
```css
nav.nav-primary li { 
    display: inline-block; 
}

nav.nav-secondary li,
nav.nav-primary li li {
    display: block;
}
```

Name all Elements and to scale and create a modular Architecture

SMACSS-style CSS (LESS):
```less
/* LESS - SMACSS and BEM */
.l-inline {
    &__item { 
        display: inline-block;
    }
}

.l-stacked {
    /* nav.nav-primary li */
    &__item { 
        display: block;
    }
    /* nav.nav-primary li li */
    &__subitem { 
        display: inline-block;
    }
}
```

```html
<nav>
    <ul class="l-inline">
        <li class="l-inline__item"><a href="https://www.tnado.com/">Home</a></li>
    </ul>
</nav>

<nav>
    <ul class="l-stacked">
        <li class="l-stacked__item">
            <a href="https://www.tnado.com/">Home</a>
            <ul class="l-stacked__subitem">
                <li class="l-inline__item"><a href="https://www.tnado.com/">Home</a></li>
            </ul>
        </li>
    </ul>
</nav>
```

## Mix

> OCSS - ACSS - BEM - SMACSS

Better, you do this:
```css
/* Prefix "m-" for module */
.m-button {

  width: 200px;
  height: 50px;

    /* Elements */
    &__small {
        width: 100px;
    }

    /* Modifiers */
    &--default {

      border: solid 1px #ccc;
      background: linear-gradient(#ccc, #222);
      box-shadow: rgba(#000000,.5) 2px 2px 5px;
    }

    &--primary {

      border: solid 1px #ddd;
      background: linear-gradient(#ddd, #333);
      box-shadow: rgba(#ffffff,.5) 2px 2px 5px;
    }
}

/** 
 * Prefix "l-" layout prefixer 
 * l-"p--" padding modifier
 * l-p--"10" 10px padding
 */
.l-p {
    &--10 {
        padding: 10px;
    }
    &--20 {
        padding: 20px;
    }
}
```

```html
<button class="m-button m-button__small m-button__default l-p--10">Send</button>
```

## Contribute

Please an [issue](https://github.com/prod3v3loper/less-mixins/issues) if you
think something could be improved. Please submit Pull Requests when ever
possible.

## Built with

* [NetBeans](https://netbeans.org/) - NetBeans editor for error-free code

## Authors

* **Samet Tarim** - *All works* - [prod3v3loper](https://www.tnado.com/author/prod3v3loper/)

## License

[GNU](https://github.com/prod3v3loper/acss-bem-oocss-smacss/blob/master/LICENSE)