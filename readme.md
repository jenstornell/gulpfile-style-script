# gulpfile.js for Gulp 4

## Sass

Sass-files saved in `assets/css/src` will be merged and converted to css and put into `assets/css/dist`.

## Javascript

Javascript-files saved in `assets/js/src` will be merged and minified and put into `assets/js/dist`.

## Install

1. Install Node
1. Install Gulp
1. Run `gulp watch` to watch for file changes.

```js
var gulp = require("gulp"),
    sass = require("gulp-sass"),
    autoprefixer = require("gulp-autoprefixer"),
    concat = require("gulp-concat");

let uglify = require('gulp-uglify-es').default;

var paths = {
    styles: {
        src: "assets/css/src/**/*.scss",
        dest: "assets/css/dist"
    },
    scripts: {
        src: "assets/js/src/**/*.js",
        dest: "assets/js/dist"
    }
};

function style() {
    return (
        gulp
            .src(paths.styles.src)
            .pipe(concat('style.min.scss'))
            .pipe(sass())
            .on("error", sass.logError)
            .pipe(autoprefixer())
            .pipe(gulp.dest(paths.styles.dest))
    );
}

function script() {
    return (
        gulp
            .src(paths.scripts.src)
            .pipe(concat('script.min.js'))
            .pipe(uglify())
            .pipe(gulp.dest(paths.scripts.dest))
    );
}

function watch(){
    gulp.watch(paths.styles.src, style);
    gulp.watch(paths.scripts.src, script);
}

exports.style = style;
exports.script = script;
exports.watch = watch;
```
