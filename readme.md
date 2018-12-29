# gulpfile.js for Gulp 4

## SASS

SASS-files saved in `assets/css/src` will be merged and converted to CSS and put into `assets/css/dist`.

## Javascript

Javascript-files saved in `assets/js/src` will be merged and minified and put into `assets/js/dist`.

### 1. Install NodeJS

[Download](https://nodejs.org/en/) and install NodeJS.

### 2. Install Gulp

#### All packages for both CSS and JS

```text
npm install --save-dev gulp gulp-sass gulp-autoprefixer gulp-concat gulp-uglify-es gulp-csso gulp-rename
```

#### Only CSS packages

```text
npm install --save-dev gulp gulp-sass gulp-autoprefixer gulp-concat gulp-csso gulp-rename
```

#### Only JS packages

```text
npm install --save-dev gulp gulp-concat gulp-uglify-es gulp-rename
```

### 3. Place your gulpfile.js

Place your `gulpfile.js` in your project, often at the root.

### 4. Run

Run `gulp` to watch for file changes.

When saving files in `assets/css/src` or `assets/js/src`, they should be converted and placed into the `dist` folders.

## Donate

Donate to [DevoneraAB](https://www.paypal.me/DevoneraAB) if you want.

## License

MIT