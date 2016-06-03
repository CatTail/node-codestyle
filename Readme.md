# node-codestyle

> Code style for Node.js project

## Table Of Content

* [Naming Conventions](#naming-conventions)
* [Requires](#requires)
* [Strict](#strict)

## Requires

Organize your node requires in the following order:

1. core modules
2. npm modules
3. others

```js
// bad
var Car = require('./models/Car')
var async = require('async')
var http = require('http')

// good
var http = require('http')
var fs = require('fs')

var async = require('async')
var mongoose = require('mongoose')

var Car = require('./models/Car')
```

## Naming Conventions

Use a leading underscore `_` when naming private properties.

```js
// bad
this.__firstName__ = 'Panda'
this.firstName_ = 'Panda'

// good
this._firstName = 'Panda'
```

Use a postfix `Async` when naming function return promise (or async functions).

```
function readFileAsync(...) {
    return new Promise((resolve, reject) => {
        fs.readFile(..., (err, data) => {
            if (err) {
                return reject(err)
            }
            resolve(data)
        })
    })
}

async function readdirAsync(...) {
    return new Promise((resolve, reject) => {
        fs.readdir(..., (err, data) => {
            if (err) {
                return reject(err)
            }
            resolve(data)
        })
    })
}
```

## Strict

Use `'use strict'` in every Node.js module to support keyword like `let` and [avoid certain mistakes](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Strict_mode#Changes_in_strict_mode).
