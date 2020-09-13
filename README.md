# web3-core-promievent

[![NPM Package][npm-image]][npm-url] [![Dependency Status][deps-image]][deps-url] [![Dev Dependency Status][deps-dev-image]][deps-dev-url]

This is a sub-package of [web3.js][repo].

This is the PromiEvent package used to return a EventEmitter mixed with a Promise to allow multiple final states as well as chaining.

Please read the [documentation][docs] for more.

## Usage

```js
import Web3PromiEvent from 'https://deno.land/x/npm_web3_core_promievent@0.0.1/mod.js';

const myFunc = function(){
    const promiEvent = Web3PromiEvent();
    
    setTimeout(function() {
        promiEvent.eventEmitter.emit('done', 'Hello!');
        promiEvent.resolve('Hello!');
    }, 10);
    
    return promiEvent.eventEmitter;
};

// and run it
myFunc()
  .on('done', console.log)
  .then(console.log);
```

## TODO
- [ ] Add tests
- [ ] Add types

[docs]: http://web3js.readthedocs.io/en/1.0/
[repo]: https://github.com/ethereum/web3.js
[npm-image]: https://img.shields.io/npm/v/web3-core-promievent.svg
[npm-url]: https://npmjs.org/package/web3-core-promievent
[deps-image]: https://david-dm.org/ethereum/web3.js/1.x/status.svg?path=packages/web3-core-promievent
[deps-url]: https://david-dm.org/ethereum/web3.js/1.x?path=packages/web3-core-promievent
[deps-dev-image]: https://david-dm.org/ethereum/web3.js/1.x/dev-status.svg?path=packages/web3-core-promievent
[deps-dev-url]: https://david-dm.org/ethereum/web3.js/1.x?type=dev&path=packages/web3-core-promievent
