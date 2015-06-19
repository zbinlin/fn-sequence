# fn-sequence


## Install

```
npm install fn-sequence
```


## Usage

```javascript
var sequence = require("fn-sequence");
sequence([
    function (value, next) {
        console.log(value); // 100
        next();
    },
    function (value, next) {
        next(null, value, "bar");
    },
    {
        foo: function (value, next) {
            next(null, "foo");
        },
        bar: function (value, next) {
            next(null, "bar");
        }
    }
], 100, function (err, val) {
    console.log(val); // "bar"
});
```
