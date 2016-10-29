# ACSS - BEM - OOCSS - SMACSS (template)

![alt text](https://img.shields.io/badge/build-passing-brightgreen.svg "Build passing")
![alt text](https://img.shields.io/badge/license-CCO-blue.svg "CCO 1.0")

> Atomic CSS (ACSS)
> Block, Element, Modifier (BEM)
> Object Oriented CSS (OOCSS)
> Scalable Modular Architecture CSS (SMACSS)

* [Tests Preview](test/img/tests.png)

### This repository has some folder and file structure for you:

```less
less/
|- _base/
|  |- _config.less
|  |- _default.less
|  |- _mixin.less (less-mixins)
|  |- ... add more ...
|
|- _layout/
|  |- _l-default.less
|  |- _l-float.less
|  |- _l-margin.less
|  |- _l-grid.less (css-grids)
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

_mixin.less [(less-mixins)](https://github.com/Samettarim/less-mixins/)

###### _layout

[_l-default.less](less/_layout/_l-default.less)

[_l-float.less](less/_layout/_l-float.less)

[_l-margin.less](less/_layout/_l-margin.less)

_l-grid.less [(css-grids)](https://github.com/Samettarim/css-grids/)

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

## OOCSS

> Separation of Structure From Skin

[More OOCSS (smashingmagazine)](https://www.smashingmagazine.com/2011/12/an-introduction-to-object-oriented-css-oocss/)

Here an ID was used and to which the skin was still defined
Don't do this:
```css
#button {

  width: 200px;
  height: 50px;
  padding: 10px;
  border: solid 1px #ccc;
  background: linear-gradient(#ccc, #222);
  box-shadow: rgba(#000000,.5) 2px 2px 5px;
}
```

Good, you do this:
```css
.button {
  width: 200px;
  height: 50px;
}

.skin {
  border: solid 1px #ccc;
  background: linear-gradient(#ccc, #222);
  box-shadow: rgba(#000000,.5) 2px 2px 5px;
}

.p10 {
    padding: 10px;
}
```

###### Mix OCSS ACSS BEM SMACSS

Better, you do this:
```css
/* Prefix "m-" for module */
.m-button {

  width: 200px;
  height: 50px;
}

.m-button--default {

  border: solid 1px #ccc;
  background: linear-gradient(#ccc, #222);
  box-shadow: rgba(#000000,.5) 2px 2px 5px;
}

.m-button--primary {

  border: solid 1px #ddd;
  background: linear-gradient(#ddd, #333);
  box-shadow: rgba(#ffffff,.5) 2px 2px 5px;
}

/** 
 * Prefix "l-" for layout 
 * l-"p-" for padding
 * l-p-"-10" for 10px
 */
.l-p--10 {

    padding: 10px;
}
```

## Contribute

Please an [issue](https://github.com/Samettarim/less-mixins/issues) if you
think something could be improved. Please submit Pull Requests when ever
possible.

## Built with

* [NetBeans](https://netbeans.org/) - NetBeans editor for error-free code

## Authors

* **Samet Tarim** - *All works* - [ProDeveloper](https://profiles.wordpress.org/prodeveloper/)

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](http://creativecommons.org/publicdomain/zero/1.0/)