# hsd-ledger

This is a client library for [ledger-app-hns][hns]. It uses primitives
from [hsd][hsd].

## Install
```
$ git clone https://github.com/boymanjor/hsd-ledger.git
$ cd hsd-ledger
$ npm install
$ npm install --no-save path/to/hsd
```

>Note: `hsd` is a peer dependency. The above command assumes you already
have an `hsd` repository cloned on your development machine and have checked
out the following commit: `ff133262ae7b83dbe86c4d96c55cca5451743bf0`.
Currently, the hsd `master` branch does not support hardware signing.
The aforementioned commit supports hardware signing, but **should only be
used to test this library**.

## Usage

Currently, we only support Node.js. We have plans to support browser
usage through WebUSB. Example usage can be found and run using the
following files:

- [examples/getAppVersion.js][app] - Get the application version number.
- [examples/getAccountXPUB.js][acc] - Get a BIP44 account xpub.
- [examples/getXPUB.js][xpub] - Get an arbitrary xpub.
- [examples/getAddress.js][addr] - Get a BIP44 compliant address.
- [examples/getPublicKey.js][pub] - Get a BIP44 compliant address.
- [examples/signTransaction-p2pkh.js][p2pkh] - Sign P2PKH transaction.
- [examples/signTransaction-p2sh.js][p2sh] - Sign P2SH transaction.

[app]: ./examples/getAppVersion.js
[acc]: ./examples/getAccountXPUB.js
[xpub]: ./examples/getXPUB.js
[addr]: ./examples/getAddress.js
[pub]: ./examples/getPublicKey.js
[p2pkh]: ./examples/signTransaction-p2pkh.js
[p2sh]: ./examples/signTransaction-p2sh.js

## Tests
### Unit tests
```bash
$ npm test
```

### End-to-end tests

For all end-to-end tests, a `LOG_LEVEL` environment variable can be set
to control the log output. Possible log levels include: `none`, `info`,
`warning`, `debug`, `error`, `spam`.


>Note: the end-to-end tests require a connected Ledger Nano S using the
seed phrase:
```
abandon abandon abandon abandon abandon abandon
abandon abandon abandon abandon abandon about
```

#### Using Ledger Nano S
```bash
$ npm run test-hid
```

#### Using Ledger Nano S and hsd
```bash
$ npm run test-hsd
```

## Contribution and License Agreement

If you contribute code to this project, you are implicitly allowing your code
to be distributed under the MIT license. You are also implicitly verifying that
all code is your original work. `</legalese>`

## License

- Copyright (c) 2018, Boyma Fahnbulleh (MIT License).

This project is a fork of [bledger][bledger].

### bledger

- Copyright (c) 2018, The Bcoin Developers (MIT License).

See LICENSE for more info.

[hns]: https://github.com/boymanjor/ledger-app-hns
[hsd]: https://github.com/handshake-org/hsd
[bledger]: https://github.com/bcoin-org/bledger
