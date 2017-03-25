# api documentation for  [through2 (v2.0.3)](https://github.com/rvagg/through2#readme)  [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-through2.svg)](https://travis-ci.org/npmdoc/node-npmdoc-through2)
#### A tiny wrapper around Node streams2 Transform to avoid explicit subclassing noise

[![NPM](https://nodei.co/npm/through2.png?downloads=true)](https://www.npmjs.com/package/through2)

[![apidoc](https://npmdoc.github.io/node-npmdoc-through2/build/screen-capture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-through2_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-through2/build..beta..travis-ci.org/apidoc.html)

![package-listing](https://npmdoc.github.io/node-npmdoc-through2/build/screen-capture.npmPackageListing.svg)



# package.json

```json

{
    "author": {
        "name": "Rod Vagg",
        "email": "r@va.gg",
        "url": "https://github.com/rvagg"
    },
    "bugs": {
        "url": "https://github.com/rvagg/through2/issues"
    },
    "dependencies": {
        "readable-stream": "^2.1.5",
        "xtend": "~4.0.1"
    },
    "description": "A tiny wrapper around Node streams2 Transform to avoid explicit subclassing noise",
    "devDependencies": {
        "bl": "~1.1.2",
        "faucet": "0.0.1",
        "stream-spigot": "~3.0.5",
        "tape": "~4.6.2"
    },
    "directories": {},
    "dist": {
        "shasum": "0004569b37c7c74ba39c43f3ced78d1ad94140be",
        "tarball": "https://registry.npmjs.org/through2/-/through2-2.0.3.tgz"
    },
    "gitHead": "4383b10b2cb6a32ae215760715b317513abe609f",
    "homepage": "https://github.com/rvagg/through2#readme",
    "keywords": [
        "stream",
        "streams2",
        "through",
        "transform"
    ],
    "license": "MIT",
    "main": "through2.js",
    "maintainers": [
        {
            "name": "rvagg",
            "email": "rod@vagg.org"
        },
        {
            "name": "bryce",
            "email": "bryce@ravenwall.com"
        }
    ],
    "name": "through2",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/rvagg/through2.git"
    },
    "scripts": {
        "test": "node test/test.js | faucet",
        "test-local": "brtapsauce-local test/basic-test.js"
    },
    "version": "2.0.3"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module through2](#apidoc.module.through2)
1.  [function <span class="apidocSignatureSpan">through2.</span>ctor (options, transform, flush)](#apidoc.element.through2.ctor)
1.  [function <span class="apidocSignatureSpan">through2.</span>obj (options, transform, flush)](#apidoc.element.through2.obj)



# <a name="apidoc.module.through2"></a>[module through2](#apidoc.module.through2)

#### <a name="apidoc.element.through2.ctor"></a>[function <span class="apidocSignatureSpan">through2.</span>ctor (options, transform, flush)](#apidoc.element.through2.ctor)
- description and source-code
```javascript
ctor = function (options, transform, flush) {
  if (typeof options == 'function') {
    flush     = transform
    transform = options
    options   = {}
  }

  if (typeof transform != 'function')
    transform = noop

  if (typeof flush != 'function')
    flush = null

  return construct(options, transform, flush)
}
```
- example usage
```shell
...
    this.push('tacking on an extra buffer to the end');
    cb();
  }
))
.pipe(fs.createWriteStream('/tmp/wut.txt'));
'''

<b><code>through2.ctor([ options, ] transformFunction[, flushFunction ])</code></b>

Instead of returning a 'stream.Transform' instance, 'through2.ctor()' returns a **constructor** for a custom Transform. This is
useful when you want to use the same transform logic in multiple instances.

'''js
var FToC = through2.ctor({objectMode: true}, function (record, encoding, callback) {
if (record.temp != null && record.unit == "F") {
  record.temp = ( ( record.temp - 32 ) * 5 ) / 9
...
```

#### <a name="apidoc.element.through2.obj"></a>[function <span class="apidocSignatureSpan">through2.</span>obj (options, transform, flush)](#apidoc.element.through2.obj)
- description and source-code
```javascript
obj = function (options, transform, flush) {
  if (typeof options == 'function') {
    flush     = transform
    transform = options
    options   = {}
  }

  if (typeof transform != 'function')
    transform = noop

  if (typeof flush != 'function')
    flush = null

  return construct(options, transform, flush)
}
```
- example usage
```shell
...
Or object streams:

'''js
var all = []

fs.createReadStream('data.csv')
.pipe(csv2())
.pipe(through2.obj(function (chunk, enc, callback) {
  var data = {
      name    : chunk[0]
    , address : chunk[3]
    , phone   : chunk[10]
  }
  this.push(data)
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
