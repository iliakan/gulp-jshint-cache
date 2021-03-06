
# Fast cached jshint for gulp

It uses in-memory stat cache, that's why `lint-watch` is blazing fast.

Usage:
```js
var jshint = require('gulp-jshint-cache');
var sources = './**/*.js';

gulp.task('lint', jshint({ src: sources }));

gulp.task('lint-or-die', jshint({ src: sources, dieOnError: true }));

gulp.task('lint-watch', ['lint'], function(neverCalled) {
  gulp.watch(serverSources, ['lint']);
});
```

Options:
  - `src` -- sources for `glob.src` (required)
  - `dieOnError` -- if true, the process will die with error status `1` if lint fails. Use this for git pre-commit check.
  - `jshint` -- options for `gulp-jshint`

