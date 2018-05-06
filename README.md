# [![MarketCoin Logo](https://prismprojects.biz/outside/market_logo.png)](http://prismprojects.biz/) v1.3.2 (Capricorn)

[![Build Status](https://travis-ci.org/TBD?branch=master)](https://travis-ci.org/TBD)
[![GoDoc](https://godoc.org/github.com/TBD?status.svg)](https://godoc.org/github.com/TBD)
[![Go Report Card](https://goreportcard.com/badge/github.com/TBD)](https://goreportcard.com/report/github.com/TBD)

MarketCoin is a new decentralized cloud Marketplace platform that creates a built
in token and marketplace for users, built off the SiaCoin platfrom. Leveraging smart 
contracts, client-side encryption, and sophisticated redundancy (via Reed-Solomon 
codes), MarketCoin allows users to safely store their marketplace with hosts that they 
do not know or trust.The result is a cloud based marketplace for things where sellers
compete to offer the best service or things at the lowest price. There is no barrier to entry for
hosts, anyone with things can join the network and start making money.

![UI](http://i.imgur.com/TBD)

Traditional marketplaces have a number of shortcomings. Users are limited to a
few big-name offerings: Google, Microsoft, Amazon. These companies have little
incentive to encrypt your purchase data or make it easy to switch services. They are
global monopolies, and they can lock you out or control the contents of what can
and cannot be sold.

We believe that users should choose their own products. MarketCoin achieves this 
by replacing the traditional monolithic marketplaces with a blockchain and
swarms of hosts, each of which stores an encrypted fragment of your purchase data. Since
the fragments are redundant, no single host can hold your data hostage: if
they jack up their price or go offline, you can simply purchase from a
different seller. In other words, trust is removed from the equation, and
switching to a different seller is painless. Stripped of these unfair
advantages, sellers must compete solely on the quality and price of the things
they provide.

At the core of MarketCoin is a blockchain that closely resembles Bitcoin.
Transactions are conducted in MarketCoin, a cryptocurrency. The blockchain is
what allows MarketCoin to enforce its smart contracts without relying on centralized
authority. To acquire MarketCoins, use an exchange such as TBD.

To get started with Sia, check out the guides below:

- [How to Purchase Things on MarketCoin](https://blog.TBD/getting-started-with-private-decentralized-cloud-storage-TBD)
- [How to Sell things on MarketCoin](https://blog.TBD/how-to-run-a-host-on-sia-TBD)
- [Using the MarketCoin API](https://blog.TBD/api-quickstart-guide-TBD)


Usage
-----

MarketCoin is ready for use with small sums of money and things, but
until the network has a more proven track record, we advise against using it
for large transactions.

This release comes with 2 binaries, Markd and Markc. markd is a background
service, or "daemon," that runs the MarkCoin protocol and exposes an HTTP API on
port 9980. markc is a command-line client that can be used to interact with
markd in a user-friendly way. There is also a graphical client, [MARK-UI](https://github.com/lockboxpm/MARK-UI), which
is the preferred way of using MarketCoin for most users. For interested developers,
the markd API is documented [here](doc/API.md).

markd and markc are run via command prompt. On Windows, you can just double-
click markd.exe if you don't need to specify any command-line arguments.
Otherwise, navigate to its containing folder and click File->Open command
prompt. Then, start the siad service by entering `markd` and pressing Enter.
The command prompt may appear to freeze; this means markd is waiting for
requests. Windows users may see a warning from the Windows Firewall; be sure
to check both boxes ("Private networks" and "Public networks") and click
"Allow access." You can now run `markc` (in a separate command prompt) or MARK-
UI to interact with markd. From here, you can send money, post or purchase
things, and advertise yourself as a seller.

Building From Source
--------------------

To build from source, [Go 1.10 must be installed](https://golang.org/doc/install)
on the system. Make sure your `$GOPATH` is set, and then simply use `go get`:

```
go get -u github.com/lockbox/MARK/...
```

This will download the MARK repo to your `$GOPATH/src` folder and install the
`markd` and `markc` binaries in your `$GOPATH/bin` folder.

To stay up-to-date, run the previous `go get` command again. Alternatively, you
can use the Makefile provided in this repo. Run `git pull origin master` to
pull the latest changes, and `make release` to build the new binaries. You
can also run `make test` and `make test-long` to run the short and full test
suites, respectively. Finally, `make cover` will generate code coverage reports
for each package; they are stored in the `cover` folder and can be viewed in
your browser.
