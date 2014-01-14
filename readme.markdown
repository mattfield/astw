# astw

walk the ast

*NB: This is a fork of substack's [astw](https://npmjs.org/package/astw) module modified to
allow passing of esprima parse options. All credit for the module goes to substack.*

# example

``` js
var astw = require('astw-opts');
var deparse = require('escodegen').generate;
var walk = astw('4 + beep(5 * 2)', { loc: true });

walk(function (node) {
    var src = deparse(node);
    console.log(node.type + ' :: ' + JSON.stringify(src));
});
```

# methods

``` js
var astw = require('astw')
```

## var walk = astw(src[, opts])

Return a `walk()` function from the source string or ast object `src` with optional
parse config options for esprima.

## walk(cb)

Walk the nodes in the ast with `cb(node)` where `node` is each element in the
ast from [esprima](http://esprima.org/) but with an additional `.parent`
reference to the parent node.

# install

With [npm](https://npmjs.org) do:

```
npm install astw-opts
```

# license

MIT
