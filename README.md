# es6-comprehensions

Compiles JavaScript array comprehensions (proposed in ES6) to ES5-compatible syntax. For instance:

```js
var squared = [ for (x of [1,2,3,4,5]) if (x > 2) x * x ];
```

compiles to:

```js
var squared = (function() {
  var result = [];

  for (var $$i0 = 0, $$arr0 = [1,2,3,4,5], $$len0 = $$arr0.length, x; $$i0 < $$len0; $$i0++) {
    x = $$arr0[$$i0];

    if (x > 2) {
      result.push(x * x);
    }
  }

  return result;
})();
```

For more information check out [the current draft for ECMAScript 6](http://people.mozilla.org/~jorendorff/es6-draft.html#sec-array-comprehension).

Please notice that the syntax has changed and many resources is still using old one.

## Installation

```
$ npm install es6-comprehensions
```

## Support

Array comprehensions progressed to the Draft ECMAScript 6 Specification. It doesn't mean that there will be no changes or that array comprehensions will be included in the final ES6 Specification.

ES6 defines also [iterators](http://tc39wiki.calculist.org/es6/iterators/) that can be used together with [for-of loops](http://tc39wiki.calculist.org/es6/for-of/) that can be used in array comprehensions. This translator does **not** support iterators in `for-of` loops. It translates `for-of` loops to plain `for` loops. Thus, it supports only plain JS arrays.

## TODO

* Consider replacing plain `for` loop with `forEach` method. It will result in more compact code,
* Consider migration to escodegen.

## Development

1. Clone the repository.
2. Run `npm install`.
3. Do your changes.

Pull requests are highly appreciated.

## License

BSD
