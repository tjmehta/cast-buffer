# cast-buffer
cast strings, arrays, and objects to buffers

# Installation
```bash
npm i --save cast-buffer
```

# Usage
```js
var buff

buff = castBuffer({ 'foo': 1, 'bar': 2 }) // new Buffer('{ 'foo': 1, 'bar': 2 }')
buff = castBuffer([ 'foo', 'bar', 'qux' ]) // new Buffer('[ 'foo', 'bar', 'qux' ]')
buff = castBuffer('hello') // new Buffer('hello')
buff = castBuffer(new Buffer('hello')) // returns same buffer

// Calls toJSON if it exists
var foobar = {
  _json: {}
  get: function () {/*...*/}
  set: function () {/*...*/}
  toJSON: function () {
    return this._json
  }
}
buff = castBuffer(foobar) // new Buffer('{}')
buff = castBuffer([ foobar ]) // new Buffer('[{}]')
```

# License
MIT