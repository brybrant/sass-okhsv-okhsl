# OkHSV / OkHSL to RGB Sass Functions

Sass functions to convert OkHSV and OkHSL to sRGB.

Credit to [Björn Ottosson](https://bottosson.github.io/posts/colorpicker/)

## Install

```bash
$ npm i -D github:brybrant/sass-okhsv-okhsl
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

  - `$hue` - Default: `0deg`\
    Number (in degrees) representing the color's hue angle in **OkHSV** color space.

  - `$saturation` - Default: `1`\
    Float (between 0 and 1) or percentage representing the color's saturation.\
    1 or 100% is completely saturated, while 0 is completely unsaturated (gray).

  - `$value` - Default: `1`\
    Float (between 0 and 1) or percentage representing the color's brightness.\
    1 or 100% is completely bright, while 0 is completely black.

  - `$alpha` - Default: `1`\
    Float (between 0 and 1) or percentage representing the color's transparency.\
    1 or 100% is completely opaque, while 0 is completely transparent.

  #### Usage example

  ```scss
  @debug okhsv_to_rgba(29deg, 1, 100%); // rgb(255, 0, 4)

  @debug okhsv_to_rgba($hue: 170); // rgb(0, 255, 201)
  ```
___

### `okhsl_to_rgba( $hue, $saturation, $lightness, $alpha )`

  Converts **OkHSL** color space to sRGB color space.

  - `$hue` - Default value: `0deg`\
    Number (in degrees) representing the color's hue angle in **OkHSL** color space.

  - `$saturation` - Default value: `1`\
    Float (between 0 and 1) or percentage representing the color's saturation.\
    1 or 100% is completely saturated, while 0 is completely unsaturated (gray).

  - `$lightness` - Default value: `0.5`\
    Float (between 0 and 1) or percentage representing the color's lightness.\
    1 or 100% is white, 0 is black, and 0.5 or 50% is "normal".

  - `$alpha` - Default value: `1`\
    Float (between 0 and 1) or percentage representing the color's transparency.\
    1 or 100% is completely opaque, while 0 is completely transparent.

  #### Usage example

  ```scss
  @debug okhsl_to_rgba(265, 100%, 0.37); // rgb(14, 3, 255)

  @debug okhsl_to_rgba($lightness: 40%); // rgb(172, 0, 89)
  ```
___

### `color_to_hex( $color )`

  Converts any color to hexadecimal format

  - `$color`\
    Any valid CSS color (rgb, hsl, etc.)

  #### Usage example

  ```scss
  @debug color_to_hex(okhsv_to_rgba(143deg, 1, 1, 0.5)); // #00FF1F80

  @debug color_to_hex(rgb(0 255 31 / 0.5)); // #00FF1F80
  ```
