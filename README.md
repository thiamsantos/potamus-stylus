# potamus-stylus

[![Greenkeeper badge](https://badges.greenkeeper.io/thiamsantos/potamus-stylus.svg)](https://greenkeeper.io/)
Stylus mixins for [potamus](https://github.com/thiamsantos/potamus) components.

```$ npm install --save-dev potamus-stylus```

Until now, there the following components:
- button
- checkbox
- radio
- text-field

Is fully recommended the use of [autoprefixer-stylus](https://github.com/jescalan/autoprefixer-stylus) along with potamus-stylus.

## Usage
### Import
``` stylus
@import 'path-to-potamus-stylus/potamus.styl'
```
### Gulp
To use with gulp just first install the npm package and then add to use add to your gulpfile as a plugin of stylus.
``` javascript
const gulp    = require('gulp')
    , stylus  = require('gulp-stylus')
    , plumber = require('gulp-plumber')
    , potamus = require('potamus-stylus');

gulp.task('stylus', () =>
  gulp.src('src/*.styl')
    .pipe(plumber())
    .pipe(stylus({
      use: [potamus()]
    }))
    .pipe(gulp.dest('dist/')));
```
### Stylus cli
`$ stylus --use potamus-stylus src -o dist`

## Components
For all components mixins you must pass a object as argument, if a blank object was passed potamus will use his default configurations.

### Button
``` html
<button class="some-awesome-button-class-name">Button</button>
```
```stylus
.some-awesome-button-class-name
  button({
    background: #E91E63, // background-color of the button
    color: #fff,         // text-color of the button
    ripple-name: effect, // class name for the ripple effect
    js: true             // if true classes needed for js interactions are added
    width: 300px         // width of the button, can be omitted
  })
```
### Checkbox
```html
<input class="some-awesome-checkbox-class-name" type="checkbox">
```
```stylus
.some-awesome-checkbox-class-name
  checkbox({
    border-color: #ccc, // border color when the checkbox is unchecked
    color: #E91E63,     // color when the checkbox is checked
    size: 40px          // size of the checkbox
  })
```
### Radio
```html
<input class="some-awesome-radio-name" type="radio" id="first" name="radio">
<input class="some-awesome-radio-name" type="radio" id="second" name="radio">
```
```stylus
.some-awesome-radio-name
  radio({
    animation-name: radio-fade, // name of the animation of the radio
    border-color: #9E9E9E,      // border color when the radio is unchecked
    color: #F44336,             // color when the radio is checked
    size: 30px                  // size of the checkbox
  })
```
### Text-field
```html
<div class="some-awesome-text-field-name">
  <input class="some-awesome-text-field-name_sufix-input" type="text">
  <label class="some-awesome-text-field-name__sufix-label">Nome</label>
</div>
```
```stylus
.some-awesome-text-field-name
  text-field({
    active-color: #2196F3,                 // color when the input is focused
    default-color: #9E9E9E,                // color when the input is closed
    input-name: _sufix-input,              // sufix for input class name
    js: true,                              // if true classes needed for js
                                           // // interactions are added
    label-name: __sufix-label,             // sufix for label class name
    primary-text-color: rgba(0,0,0,.87),   // color of text on input an label
    secondary-text-color: rgba(0,0,0,.54), // color of text when label is closed
    valid-color: #4CAF50                   // color when the input is valid
  })
```
## Contributing
- Fork it!
- Create a new branch for the new feature: `git checkout -b my-new-feature`
- Commit your changes: `git commit -m 'Add some feature'`
- Push to the branch: `git push origin my-new-feature`
- Submit a pull request with full remarks documenting your changes ;)

## License

potamus is released under the terms of the [MIT License](https://opensource.org/licenses/MIT)
