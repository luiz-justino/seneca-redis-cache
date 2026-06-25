![Seneca](http://senecajs.org/files/assets/seneca-logo.png)
> A [Seneca.js][] plugin

# @seneca/redis-cache

| ![Voxgig](https://www.voxgig.com/res/img/vgt01r.png) | This open source module is sponsored and supported by [Voxgig](https://www.voxgig.com). |
|---|---|

## Install

```sh
npm install seneca
npm install seneca-redis-cache
```

### Quick example

This code snippet sets a value and then retrieves it.

```js
var seneca = require('seneca')();
seneca.use('redis-cache');

seneca.ready(function(err) {
  seneca.act({role: 'cache', cmd: 'set', key: 'k1', val: 'v1'}, function(err) {
    seneca.act({role: 'cache', cmd: 'get', key: 'k1'}, function(err, out) {
      console.log('value = ' + out)
    });
  });
});
```


<!--START:options-->

## Quick Example

```js
require('seneca')()
  .use('seneca-redis-cache', { host: 'localhost', port: 6379 })
```

## More Examples

See [test/](test/) for usage examples.

## Motivation

Redis caching plugin for the Seneca framework.

## Support

If you're using this module and need help, you can:

- Post a [github issue][]
- Tweet to [@senecajs][]

## API

### Options

* `expire` : number <i><small>3600</small></i>
* `redis.port` : number <i><small>6379</small></i>
* `redis.host` : string <i><small>"127.0.0.1"</small></i>


Set plugin options when loading with:
```js


seneca.use('redis-cache', { name: value, ... })


```


<small>Note: <code>foo.bar</code> in the list above means 
<code>{ foo: { bar: ... } }</code></small> 



<!--END:options-->

<!--START:action-list-->

### Action Patterns

* [init:redis-cache](#-initrediscache-)
* [role:cache,cmd:add](#-rolecachecmdadd-)
* [role:cache,cmd:clear](#-rolecachecmdclear-)
* [role:cache,cmd:decr](#-rolecachecmddecr-)
* [role:cache,cmd:delete](#-rolecachecmddelete-)
* [role:cache,cmd:get](#-rolecachecmdget-)
* [role:cache,cmd:incr](#-rolecachecmdincr-)
* [role:cache,cmd:set](#-rolecachecmdset-)
* [role:cache,get:native](#-rolecachegetnative-)


<!--END:action-list-->

<!--START:action-desc-->

## Contributing

The [Senecajs org][] encourages open participation. If you feel you can help in any way, be it with documentation, examples, extra testing, or new features please get in touch.

The [Senecajs org][] encourage open participation. If you feel you can help in any way, be it with
documentation, examples, extra testing, or new features please get in touch.

### Running tests

```sh
npm run test
```

## Background

Uses [ioredis](https://github.com/luin/ioredis) as the Redis client.

[![npm version][npm-badge]][npm-url]
[![Build Status][travis-badge]][travis-url]
[![Coveralls][BadgeCoveralls]][Coveralls]
[![Maintainability](https://api.codeclimate.com/v1/badges/36abf0f68317851f768d/maintainability)](https://codeclimate.com/github/senecajs/seneca-redis-cache/maintainability)
[![DeepScan grade](https://deepscan.io/api/teams/5016/projects/12816/branches/203962/badge/grade.svg)](https://deepscan.io/dashboard#view=project&tid=5016&pid=12816&bid=203962)
[![Dependency Status][david-badge]][david-url]
[![Gitter][gitter-badge]][gitter-url]
[npm-badge]: https://img.shields.io/npm/v/seneca-redis-cache.svg
[npm-url]: https://npmjs.com/package/seneca-redis-cache
[travis-badge]: https://travis-ci.org/senecajs/seneca-redis-cache.svg
[travis-url]: https://travis-ci.org/senecajs/seneca-redis-cache
[codeclimate-badge]: https://codeclimate.com/github/senecajs/seneca-redis-cache/badges/gpa.svg
[codeclimate-url]: https://codeclimate.com/github/senecajs/seneca-redis-cache
[Coveralls]: https://coveralls.io/github/senecajs/seneca-redis-cache?branch=master
[BadgeCoveralls]: https://coveralls.io/repos/github/senecajs/seneca-redis-cache/badge.svg?branch=master
[david-badge]: https://david-dm.org/senecajs/seneca-redis-cache.svg
[david-url]: https://david-dm.org/senecajs/seneca-redis-cache
[gitter-badge]: https://badges.gitter.im/Join%20Chat.svg
[gitter-url]: https://gitter.im/senecajs/seneca
[MIT]: ./LICENSE
[Senecajs org]: https://github.com/senecajs/
[Seneca.js]: https://www.npmjs.com/package/seneca
