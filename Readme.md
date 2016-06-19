# SimpleStorage Ethereum Contract

This is an example on how to embed an Ethereum Solidity Smart-Contract into an NPM module, as the contract file is just a `.sol` file, it can be saved inside a module.

Then, to use it in your app (DAPP), you just need to install it:

    npm i --save simple-storage-contract

(you have to have a `package.json` file with at least `{}` written in it)

And then you can use it (examples are in coffeescript).

Compilation:

```coffee
# compile.coffee

solc = require 'solc'
fs   = require 'fs'
c    = console


code = fs.readFileSync "./node_modules/simple-storage-contract/simple_storage.sol"
code = code.toString()

contracts = solc.compile code
contracts = JSON.stringify contracts
fs.writeFileSync './config/contracts.json', contracts

```

Usage:

TODO: example to load the contract and call the set and get methods

```coffee
# deploy contract

# call public methods on contract address
#   - set
#   - data (property)
```

You can use this simple module as base for your own npm module.

The idea is that you can share contracts with others by just pushing them to `npm` and being able to resolve their dependencies and update them via `npm install`.

You can use `cp` commands or symlinks to have all the contracts in the same directory so they can be compiled in one go by `solc` (c++ version) too or use the `solc` NPM module like in the example above.


Enjoy,

@makevoid
