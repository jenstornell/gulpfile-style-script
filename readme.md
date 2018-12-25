# gulpfile.js for Gulp 4

```js
var gulp = require("gulp"),
    sass = require("gulp-sass"),
    autoprefixer = require("gulp-autoprefixer"),
    concat = require("gulp-concat");

let uglify = require('gulp-uglify-es').default;

var paths = {
    styles: {
        src: "assets/css/src/**/*.scss",
        dest: "assets/css/dest"
    },
    scripts: {
        src: "assets/js/src/**/*.js",
        dest: "assets/js/dest"
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
