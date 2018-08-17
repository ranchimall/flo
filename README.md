FLO Core integration/staging tree
=====================================

[![Build Status](https://travis-ci.org/floblockchain/flo.svg?branch=master)](https://travis-ci.org/floblockchain/flo)

https://flo.cash

What is FLO?
----------------

FLO is an experimental digital currency that enables instant payments to
anyone, anywhere in the world. FLO uses peer-to-peer technology to operate
with no central authority: managing transactions and issuing money are carried
out collectively by the network. FLO Core is the name of open source
software which enables the use of this currency.

For more information, as well as an immediately useable, binary version of
the FLO Core software, see [https://flo.cash](https://flo.cash).

License
-------

FLO Core is released under the terms of the MIT license. See [COPYING](COPYING) for more
information or see https://opensource.org/licenses/MIT.

Development Process
-------------------

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/floblockchain/flo/tags) are created
regularly to indicate new official, stable release versions of FLO Core.

The contribution workflow is described in [CONTRIBUTING.md](CONTRIBUTING.md).


Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test on short notice. Please be patient and help out by testing
other people's pull requests, and remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write [unit tests](src/test/README.md) for new code, and to
submit new unit tests for old code. Unit tests can be compiled and run
(assuming they weren't disabled in configure) with: `make check`. Further details on running
and extending unit tests can be found in [/src/test/README.md](/src/test/README.md).

There are also [regression and integration tests](/test), written
in Python, that are run automatically on the build server.
These tests can be run (if the [test dependencies](/test) are installed) with: `test/functional/test_runner.py`

The Travis CI system makes sure that every pull request is built for Windows, Linux, and OS X, and that unit/sanity tests are run automatically.

### Manual Quality Assurance (QA) Testing

Changes should be tested by somebody other than the developer who wrote the
code. This is especially important for large or high-risk changes. It is useful
to add a test plan to the pull request description if testing the changes is
not straightforward.

Translations
------------

We only accept translation fixes that are submitted through [Bitcoin Core's Transifex page](https://www.transifex.com/projects/p/bitcoin/).
Translations are converted to FLO periodically.

Translations are periodically pulled from Transifex and merged into the git repository. See the
[translation process](doc/translation_process.md) for details on how this works.

**Important**: We do not accept translation changes as GitHub pull requests because the next
pull from Transifex would automatically overwrite them again.

Upgrades
--------
For the pre-compiled executable version of FLO, check **bin/** directory

### Added 2 features to the FLO wallet :
1. CoinControlFIFO - selects the coins that were received first to be spent first (First-In-First-Out).
To enable it: add **CoinControlFIFO=1** in flo.conf (or) pass **-CoinControlFIFO** as cmdline arg 


2. SendChangeToBack - send the change back to the coin's original address
To enable it, add **SendChangeToBack=1** in flo.conf (or) pass **-SendChangeToBack** as cmdline arg

### Added Multi-Wallet support for Linux :
Multi-wallet support allows the user to run more than 1 wallet simultaneously.
The Multi-wallet executable file is located in **bin/Linux**
To access multi-wallet run :

	./multiWallet -create [walletName]
	./multiWallet <walletName> <command> [option]

For more details run :

	./multiWallet -help





