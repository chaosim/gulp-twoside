gulp-twoside is a [Gulp](https://github.com/gulpjs/gulp) extension to add wrap files for [twoside.js](https://github.com/chaosim) module.  [Gulp is a streaming build system](https://github.com/gulpjs/gulp) utilizing [node.js](http://nodejs.org/).

```javascript
var twoside = require('gulp-twoside');
```

## Usage

```javascript
var twoside = require('gulp-twoside');

gulp.src('./foo/*.js')
  .pipe(twoside('foo', 'foo'))
  .pipe(gulp.dest('./dist/')

gulp.src('./foo/*.js')
  .pipe(twoside('foo', 'bar', { hello : 'halo'} ))
  .pipe(gulp.dest('./dist/')

gulp.src('./foo/bar/*.js')
  .pipe(twoside('foo/bar', 'bar', { hello : 'halo', only_wrap_for_browser: true} ))
  .pipe(gulp.dest('./dist/')


## API

### twoside(basePath, packageName, pathMap)

#### basePath

Type: `String`  
Default: `''`  

the base path of all package files, with __dirname is omitted.


#### packageName

Type: `Object`  
Default: `{}`  

The package name, it will replace the __dirname+basePath part of file.path, as the module hashkey.

#### pathMap
if the hashkey (generated as above) is an entry of pathMap, then the hashMap[hashkey] will become the real module hash key.

an option can be set in pathMap:

only_wrap_for_browser: true: wrapped file will work normally in browser, but not work in nodejs.

See the source code for more information.

## License

```
The MIT License (MIT)

Copyright (c) 2013 Caoxingming(simeon.chaos@gmail.com)

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```
