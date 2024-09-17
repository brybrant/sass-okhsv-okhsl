# OkHSV / OkHSL to RGB Sass Functions

Sass functions to convert OkHSV and OkHSL to sRGB.

Credit to [Björn Ottosson](https://bottosson.github.io/posts/colorpicker/)

## Install

```bash
$ npm i -D @brybrant/sass-okhsv-okhsl
```

## Setup

```scss
@use '~/node_modules/@brybrant/sass-okhsv-okhsl' as convert;

$red: convert.okhsv_to_rgba(29deg, 100%, 100%); // rgb(255, 0, 4)

$blue: convert.okhsl_to_rgba(265, 100%, 0.37); // rgb(14, 3, 255)

$blue_hex: convert.color_to_hex($blue); // #0E03FF
```

## Functions

### `okhsv_to_rgba( $hue, $saturation, $value, $alpha )`

  Converts **OkHSV** color space to sRGB color space.

  - #### `$hue`
    A [`number`](https://mdn.io/css_number) or an [`angle`](https://mdn.io/angle) representing the color's [hue](https://mdn.io/hue) angle in **OkHSV** color space.\
    &#9642; Default: `0deg`

  - #### `$saturation`
    A float (between 0 and 1) or [`percentage`](https://mdn.io/percentage) representing the color's saturation.\
    `1` or `100%` is completely saturated, while `0` is completely unsaturated (gray).\
    &#9642; Default: `1`

  - #### `$value`
    A float (between 0 and 1) or [`percentage`](https://mdn.io/percentage) representing the color's brightness.\
    `1` or `100%` is completely bright, while `0` is completely black.\
    &#9642; Default: `1`

  - #### `$alpha`
    An [alpha value](https://mdn.io/alpha-value) representing the color's transparency.\
    `1` or `100%` is completely opaque, while `0` is completely transparent.\
    &#9642; Default: `1`

  #### Usage example

  ```scss
  @debug okhsv_to_rgba(29deg, 1, 100%); // rgb(255, 0, 4)

  @debug okhsv_to_rgba($hue: 170); // rgb(0, 255, 201)
  ```
___

### `okhsl_to_rgba( $hue, $saturation, $lightness, $alpha )`

  Converts **OkHSL** color space to sRGB color space.

  - #### `$hue`
    A [`number`](https://mdn.io/css_number) or an [`angle`](https://mdn.io/angle) representing the color's [hue](https://mdn.io/hue) angle in **OkHSL** color space.\
    &#9642; Default: `0deg`

  - #### `$saturation`
    A float (between 0 and 1) or [`percentage`](https://mdn.io/percentage) representing the color's saturation.\
    `1` or `100%` is completely saturated, while `0` is completely unsaturated (gray).\
    &#9642; Default: `1`

  - #### `$lightness`
    A float (between 0 and 1) or [`percentage`](https://mdn.io/percentage) representing the color's lightness.\
    `1` or `100%` is white, `0` is black, and `0.5` or `50%` is "normal".\
    &#9642; Default: `0.5`

  - #### `$alpha`
    An [alpha value](https://mdn.io/alpha-value) representing the color's transparency.\
    `1` or `100%` is completely opaque, while `0` is completely transparent.\
    &#9642; Default: `1`

  #### Usage example

  ```scss
  @debug okhsl_to_rgba(265, 100%, 0.37); // rgb(14, 3, 255)

  @debug okhsl_to_rgba($lightness: 40%); // rgb(172, 0, 89)
  ```
___

### `color_to_hex( $color )`

  Converts any color to [hexadecimal](https://mdn.io/hex-color) format.

  - #### `$color`
    Any valid [CSS color](https://mdn.io/color_value) (rgb, hsl, etc.)

  #### Usage example

  ```scss
  @debug color_to_hex(okhsv_to_rgba(143deg, 1, 1, 0.5)); // #00FF1F80

  @debug color_to_hex(rgb(0 255 31 / 0.5)); // #00FF1F80
  ```
