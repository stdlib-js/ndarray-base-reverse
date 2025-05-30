<!--

@license Apache-2.0

Copyright (c) 2023 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# reverse

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Return a view of an input ndarray in which the order of elements along each dimension is reversed.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->

<section class="installation">

## Installation

```bash
npm install @stdlib/ndarray-base-reverse
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm`][esm-url] branch (see [README][esm-readme]).
-   If you are using Deno, visit the [`deno`][deno-url] branch (see [README][deno-readme] for usage intructions).
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd`][umd-url] branch (see [README][umd-readme]).

The [branches.md][branches-url] file summarizes the available branches and displays a diagram illustrating their relationships.

To view installation and usage instructions specific to each branch build, be sure to explicitly navigate to the respective README files on each branch, as linked to above.

</section>

<section class="usage">

## Usage

```javascript
var reverse = require( '@stdlib/ndarray-base-reverse' );
```

#### reverse( x, writable )

Returns a view of an input ndarray in which the order of elements along each dimension is reversed.

```javascript
var ndarray = require( '@stdlib/ndarray-ctor' );
var ndarray2array = require( '@stdlib/ndarray-to-array' );

var buffer = [ 1.0, 2.0, 3.0, 4.0, 5.0, 6.0 ];
var shape = [ 3, 2 ];
var strides = [ 2, 1 ];
var offset = 0;

var x = ndarray( 'generic', buffer, shape, strides, offset, 'row-major' );
// returns <ndarray>

var sh = x.shape;
// returns [ 3, 2 ]

var arr = ndarray2array( x );
// returns [ [ 1.0, 2.0 ], [ 3.0, 4.0 ], [ 5.0, 6.0 ] ]

var y = reverse( x, false );
// returns <ndarray>

sh = y.shape;
// returns [ 3, 2 ]

arr = ndarray2array( y );
// returns [ [ 6.0, 5.0 ], [ 4.0, 3.0 ], [ 2.0, 1.0 ] ]
```

The function accepts the following arguments:

-   **x**: input ndarray.
-   **writable**: boolean indicating whether a returned ndarray should be writable.

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

## Notes

-   The `writable` parameter **only** applies to ndarray constructors supporting **read-only** instances.

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var array = require( '@stdlib/ndarray-array' );
var ndarray2array = require( '@stdlib/ndarray-to-array' );
var zeroTo = require( '@stdlib/array-base-zero-to' );
var reverse = require( '@stdlib/ndarray-base-reverse' );

// Create a linear ndarray buffer:
var buf = zeroTo( 16 );

// Create a one-dimensional ndarray:
var x1 = array( buf, {
    'shape': [ 16 ]
});

// Reverse element order:
var y1 = reverse( x1, false );
// returns <ndarray>

var a1 = ndarray2array( y1 );
// returns [ 15, 14, 13, 12, 11, 10, 9, 8, 7, 6, 5, 4, 3, 2, 1, 0 ]

// Create a two-dimensional ndarray:
var x2 = array( buf, {
    'shape': [ 4, 4 ]
});

// Reverse element order:
var y2 = reverse( x2, false );
// returns <ndarray>

var a2 = ndarray2array( y2 );
// returns [ [ 15, 14, 13, 12 ], [ 11, 10, 9, 8 ], [ 7, 6, 5, 4 ], [ 3, 2, 1, 0 ] ]

// Create a three-dimensional ndarray:
var x3 = array( buf, {
    'shape': [ 2, 4, 2 ]
});

// Reverse element order:
var y3 = reverse( x3, false );
// returns <ndarray>

var a3 = ndarray2array( y3 );
// returns [ [ [ 15, 14 ], [ 13, 12 ], [ 11, 10 ], [ 9, 8 ] ], [ [ 7, 6 ], [ 5, 4 ], [ 3, 2 ], [ 1, 0 ] ] ]
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2025. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/ndarray-base-reverse.svg
[npm-url]: https://npmjs.org/package/@stdlib/ndarray-base-reverse

[test-image]: https://github.com/stdlib-js/ndarray-base-reverse/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/ndarray-base-reverse/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/ndarray-base-reverse/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/ndarray-base-reverse?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/ndarray-base-reverse.svg
[dependencies-url]: https://david-dm.org/stdlib-js/ndarray-base-reverse/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/ndarray-base-reverse/tree/deno
[deno-readme]: https://github.com/stdlib-js/ndarray-base-reverse/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/ndarray-base-reverse/tree/umd
[umd-readme]: https://github.com/stdlib-js/ndarray-base-reverse/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/ndarray-base-reverse/tree/esm
[esm-readme]: https://github.com/stdlib-js/ndarray-base-reverse/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/ndarray-base-reverse/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/ndarray-base-reverse/main/LICENSE

</section>

<!-- /.links -->
