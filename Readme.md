# SimpleStorage Ethereum Contract

This is an example on how to embed an Ethereum Solidity Smart-Contract into an NPM module, as the contract file is just a `.sol` file, it can be saved inside a module.

Then, to use it in your app (DAPP), you just need to install it:

    npm i --save simple-storage-contract

(you have to have a `package.json` file with at least `{}` written in it)

And then you can use it:

```js
const web3 = // ... connect with your provider here
const solc = require('solc')
const fs   = require('fs')

const contractCode = fs.readFileSync('./node_modules/simple-storage-contract/simple_storage.sol')

const abi = solc.compileSolidity(contractCode)
// TODO

// deploy // call method // call public method on contract address

```

You can use this simple module as base for your own npm module.

The idea is that you can share contracts with others by just pushing them to `npm` and being able to resolve their dependencies and update them via `npm install`.

You can use `cp` commands or symlinks to have all the contracts in the same directory so they can be compiled in one go by `solc` (c++ version) too.


Enjoy,

@makevoid
