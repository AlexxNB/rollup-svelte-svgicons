# rollup-plugin-svg-icons

Bundles all svg icons from the speciefed folder to the single spritesheet svg file.

## Installation

```bash
npm i -D rollup-plugin-svg-icons
```

## Rollup configuration

```javascript
/* rollup.config.js */
import svgicons from 'rollup-plugin-svg-icons'

export default {
...
  plugins: [
    svgicons({
      // folder with svg-icons
      inputFolder: 'src/icons',  // it is default value

      // path for the sprite file
      output: 'dist/bundle.svg', // it is default value

      // by default svgo is disabled, to turn it on - pass config object (or just empty object)
      svgo: { /* config */ }, 
    })
    ...
  ]
  ...
}
```

## Usage in HTML

Use href `bundle.svg#iconid` where `iconid` is base part of svg-icon filename. For ex. if in source folder you have `myicon.svg` then you should use `bandle.svg#myicon`:

```html
<style>
.inline-svg-icon{
  display: inline-block;
  fill: currentColor;
  width: 24px;
  height: 24px;
  vertical-align: middle;
}
</style>

<svg class="inline-svg-icon">
  <use xlink:href="bundle.svg#iconid"></use>
</svg>
```

## Restrictions

Icons with gradients or some types of complex shapes will not be packed in the sprite correctly.

## Inspiration
Plugin based on [svgstore](https://www.npmjs.com/package/svgstore) package.

## License
MIT