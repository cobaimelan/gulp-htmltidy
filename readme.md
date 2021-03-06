
# [gulp](https://github.com/gulpjs/gulp)-htmltidy  

[![Travis Build Status](http://img.shields.io/travis/c0b41/gulp-htmltidy.svg?style=flat-square)](https://travis-ci.org/c0b41/gulp-htmltidy) [![Circle Build Status](https://img.shields.io/circleci/project/c0b41/gulp-htmltidy.svg?style=flat-square)](https://circleci.com/gh/c0b41/gulp-htmltidy) [![Appveyor Build Status](https://img.shields.io/appveyor/ci/c0b41/gulp-htmltidy.svg?style=flat-square)](https://ci.appveyor.com/project/c0b41/gulp-htmltidy) [![Build Status](https://img.shields.io/david/c0b41/gulp-htmltidy.svg?style=flat-square)](https://david-dm.org/c0b41/gulp-htmltidy) [![io.js supported](https://img.shields.io/badge/io.js-supported-green.svg?style=flat-square)](https://iojs.org)



> HTML Tidy is an open source program for checking and generating clean XHTML/HTML. It cleans up coding errors in HTML files and fixes bad formatting. It can output files in the HTML, XHTML or XML file format.

> Using HTML Tidy, developers can programatically clean up and fix poorly-written HTML pages. Another use is to convert HTML to XHTML or XML. These files can then be easily processed using the tools in the traditional XML chain, such as XSL transforms.

Uses the [htmltidy2](https://github.com/c0b41/htmltidy2) library.

## How It Works
`/path/to/file.html`:
```html
<html>
    <head>
      <style>
        p { color: red; }
      </style>
    </head>
    <body>
   		  <!-- ===== body ====== -->
     	 <p>Test</p>
            
    </body>
        <!--Default Zone
        -->
        <!--Default Zone End-->
</html>
```



Output:
```html
<!DOCTYPE html>
<html>
<head>

<style>
      p { color: red; }
</style>
<title></title>
</head>
<body>
<p>Test</p>
</body>
</html>

```


## Install

Install with [npm](https://npmjs.org/package/gulp-htmltidy)

```
npm install --save-dev gulp-htmltidy
```


## Usage

```js
var gulp = require('gulp'),
    htmltidy = require('gulp-htmltidy');

gulp.task('default', function() {
  return gulp.src('./*.html')
        .pipe(htmltidy())
        .pipe(gulp.dest('build/'));;
});
```

With options:

```js
var gulp = require('gulp'),
    htmltidy = require('htmltidy');

gulp.task('default', function() {
  return gulp.src('./*.html')
        .pipe(htmltidy({doctype: 'html5',
					   hideComments: true,
					   indent: false}))
        .pipe(gulp.dest('build/'));;
});
```

Clean html like text according optional configuration [tidy options](http://api.html-tidy.org/tidy/quickref_5.6.0.html).


## API

### htmltidy(options)


#### options.doctype

Type: `String`


#### options.hideComments

Type: `Boolean`
Default: `false`

#### options.indent

Type: `Boolean`
Default: `false`



