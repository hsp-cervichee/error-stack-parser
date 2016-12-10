error-stack-parser.js - Extract meaning from JS Errors
===============
[![Build Status](https://travis-ci.org/stacktracejs/error-stack-parser.svg?branch=master)](https://travis-ci.org/stacktracejs/error-stack-parser) [![Coverage Status](https://img.shields.io/coveralls/stacktracejs/error-stack-parser.svg)](https://coveralls.io/r/stacktracejs/error-stack-parser) [![GitHub license](https://img.shields.io/github/license/stacktracejs/error-stack-parser.svg)](http://unlicense.org)

Simple, cross-browser [Error](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error) parser.
This library parses and extracts function names, URLs, line numbers, and column numbers from the given Error's `stack` as
an Array of [StackFrame](http://git.io/stackframe)s. 

Once you have parsed out StackFrames, you can do much more interesting things. See [stacktrace-gps](http://git.io/stacktrace-gps).

Note that in IE9 and earlier, `Error` objects don't have enough information to extract much of anything. In IE 10, `Error`s
are given a `stack` once they're `throw`n.

## Browser Support
[![Sauce Test Status](https://saucelabs.com/browser-matrix/stacktracejs.svg)](https://saucelabs.com/u/stacktracejs)

## Usage
```js
ErrorStackParser.parse(new Error('BOOM'));

=> [
        StackFrame({functionName: 'foo', args: [], fileName: 'path/to/file.js', lineNumber: 35, columnNumber: 79, isNative: false, isEval: false}),
        StackFrame({functionName: 'Bar', fileName: 'https://cdn.somewherefast.com/utils.min.js', lineNumber: 1, columnNumber: 832, isNative: false, isEval: false, isConstructor: true}),
        StackFrame(... and so on ...)
   ]
```

## Installation
```bash
npm install error-stack-parser
bower install error-stack-parser
https://raw.githubusercontent.com/stacktracejs/error-stack-parser/master/dist/error-stack-parser.min.js
```

## Contributing
Want to be listed as a *Contributor*? Start with the [Contributing Guide](.github/CONTRIBUTING.md)!

