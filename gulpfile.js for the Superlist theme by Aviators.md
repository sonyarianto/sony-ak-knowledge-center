~~~
var gulp = require('./node_modules/gulp');
var sass = require('./node_modules/gulp-sass');

gulp.task('compile', function() {
    gulp.src('./assets/scss/superlist.scss')
        .pipe(sass())
        .pipe(gulp.dest('./assets/css/'));
});

gulp.task('watch', function() {
    gulp.watch('./assets/scss/*.scss', ['compile']);
    gulp.watch('./assets/scss/helpers/*.scss', ['compile']);
});
~~~

Save it as `gulpfile.js` on project directory and later run it by typing `gulp compile`.
