# regrid-scss

## Description

A simple SCSS grid framework inspired by
[Flexbox Grid](https://github.com/kristoferjoseph/flexboxgrid) and
[Bootstrap Grid](http://getbootstrap.com/examples/grid/).

Designed to crazy simple, flexible (no pun intended), and customizable.

## Installation

Either include `src/regrid.scss` in your SASS file, or include the css in `dist`
on your page.

`<link rel="stylesheet" type="text/css" href="regrid.min.css">`

## Usage

### Basic

Just add `.col` elements to a `.row` container!

Example:
```html
<div class="row">
  <div class="col"></div>
  <div class="col"></div>
  <div class="col"></div>
</div>
```

### Responsive

Classes of the format `col-{breakpoint}-{size}` work similarly to Bootstrap's
grid. Breakpoints follow small-first priority, new sizes only being applied when
the viewport reaches the minimum width defined by the breakpoints. By default,
column sizes are on a 12 unit system, and the following breakpoints are available:
- `sm`
- `md` (min-width 640px)
- `lg` (min-width 960px)
- `xl` (min-width 1200px)

Example:
```html
<div class="row">
  <div class="col-sm-12 col-md-6 col-lg-3"></div>
  <div class="col-sm-12 col-md-6 col-lg-3"></div>
  <div class="col-sm-12 col-md-6 col-lg-3"></div>
  <div class="col-sm-12 col-md-6 col-lg-3"></div>
</div>
```

### Custom

Regrid provides some SCSS mixins of the format `media-{breakpoint}` to easily
add responsive media queries to your stylesheets.

Example:
```scss
.foo {
  @include media-lg {
    /* Make background blue on large screens and up */
    background-color: blue;
  }
}
```

If you're using SCSS you can modify the number of column units as well as the
breakpoints by overriding the following variables:
```
$grid-columns
$grid-break-md
$grid-break-lg
$grid-break-xl
