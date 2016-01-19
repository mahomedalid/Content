```
gulp.task('default', function () {
    console.log('Hello world');
});
```

***

```
body {
    font-family: Arial;
    font-size: 14pt;
}

h1 {
    font-size:4rem;
    font-weight: bold;
    text-decoration: underline;
}

h2 {
    font-size:3rem;
    font-weight: bold;   
}
```

***

```
var gulp = require('gulp'),
var cssmin = require("gulp-cssmin");
var autoprefixer = require('gulp-autoprefixer');

gulp.task("cssmin", function () {
    gulp.src("css/*.css")
    .pipe(autoprefixer())
    .pipe(cssmin())
    .pipe(gulp.dest("wwwroot/css"));
});

gulp.task('csswatch', function() {
    gulp.watch('css/*.css', ['cssmin']);
});

gulp.task('default', ['cssmin', 'csswatch']);
```