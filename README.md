node-jsonnet
=====================

[![Build Status](https://travis-ci.com/legovaer/node-jsonnet.svg?branch=master)](https://travis-ci.com/legovaer/node-jsonnet)

[jsonnet](http://google.github.io/jsonnet/doc/index.html) is a DSL for JSON. Jsonnet is created by Google.

This module is a Jsonnet wrapper for Node.js

This module is a fork from [yosuke-furukawa/node-jsonnet](https://github.com/yosuke-furukawa/node-jsonnet) as it was no longer maintained.

Jsonnet demo
---------------------

before:

```json
// Jsonnet Example
{
    person1: {
        name: "Alice",
        welcome: "Hello " + self.name + "!",
    },
    person2: self.person1 { name: "Bob" },
}
```

after:

```json
{
   "person1": {
      "name": "Alice",
      "welcome": "Hello Alice!"
   },
   "person2": {
      "name": "Bob",
      "welcome": "Hello Bob!"
   }
}
```

If you would like to know more Jsonnet syntax, read here.

[http://google.github.io/jsonnet/doc/spec.html](http://google.github.io/jsonnet/doc/spec.html)

How to use
--------------------

```shell
$ npm install jsonnet --save
```

```javascript

var Jsonnet = require('jsonnet');
// instance jsonnet
var jsonnet = new Jsonnet();
var fs = require('fs');

var code = fs.readFileSync("./menu.jsonnet");

// eval jsonnet to javascript object
var result = jsonnet.eval(code);

console.log(result);
```
