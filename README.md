[![GitHub release](https://img.shields.io/github/release/oliver-zehentleitner/unicorn_fy.svg)](https://github.com/oliver-zehentleitner/unicorn_fy/releases/latest)
[![GitHub](https://img.shields.io/github/license/oliver-zehentleitner/unicorn_fy.svg?color=blue)](https://github.com/oliver-zehentleitner/unicorn_fy/blob/master/LICENSE)
[![PyPI - Python Version](https://img.shields.io/pypi/pyversions/unicorn_fy.svg)](https://www.python.org/downloads/)
[![Downloads](https://pepy.tech/badge/unicorn-fy)](https://pepy.tech/project/unicorn-fy)
[![PyPI - Status](https://img.shields.io/pypi/status/unicorn_fy.svg)](https://github.com/oliver-zehentleitner/unicorn_fy/issues)
[![PyPI - Wheel](https://img.shields.io/pypi/wheel/unicorn_fy.svg?label=PyPI%20wheel)](https://pypi.org/project/unicorn-fy/)
[![Build Status](https://travis-ci.com/oliver-zehentleitner/unicorn_fy.svg?branch=master)](https://travis-ci.com/oliver-zehentleitner/unicorn_fy)
[![Coverage Status](https://coveralls.io/repos/github/oliver-zehentleitner/unicorn_fy/badge.svg?branch=master)](https://coveralls.io/github/oliver-zehentleitner/unicorn_fy?branch=master)
[![Telegram](https://img.shields.io/badge/chat-telegram-yellow.svg)](https://t.me/unicorndevs)
[![Donations/week](http://img.shields.io/liberapay/receives/oliver-zehentleitner.svg?logo=liberapay)](https://liberapay.com/oliver-zehentleitner/donate)
[![Patrons](http://img.shields.io/liberapay/patrons/oliver-zehentleitner.svg?logo=liberapay")](https://liberapay.com/oliver-zehentleitner/donate)

# UnicornFy
[Supported Exchanges](#supported-exchanges) | [Installation](#installation-and-upgrade) | [Documentation](#documentation) | 
[Change Log](#change-log) | [Wiki](#wiki) | [Social](#social) | [Notifications](#receive-notifications) | 
[Bugs](#how-to-report-bugs-or-suggest-improvements) | [Contributing](#contributing)

Convert received raw data from crypto exchange API endpoints into well-formed python dictionaries.

[UnicornFy](https://github.com/oliver-zehentleitner/unicorn_fy) is a side project of 
[UNICORN Binance WebSocket API](https://github.com/oliver-zehentleitner/unicorn-binance-websocket-api) but can be used
with every API that delivers the receives in raw format (as received without changes).

```
from unicorn_fy.unicorn_fy import UnicornFy

received_stream_data_json = {"stream": "btcusdt@trade",
                             "data": {"e": "trade",
                                      "E": 1556876873656,
                                      "s": "BTCUSDT",
                                      "t": 117727701,
                                      "p": "5786.76000000",
                                      "q": "0.03200500",
                                      "b": 341831847,
                                      "a": 341831876,
                                      "T": 1556876873648,
                                      "m": True,
                                      "M": True}}

unicorn_fied_stream_data = UnicornFy.binance_com_websocket(received_stream_data_json)
print(unicorn_fied_stream_data)
>>>
{'stream_type': 'btcusdt@trade', 'event_type': 'trade', 'event_time': 1556876873656, 'symbol': 'BTCUSDT', 'trade_id': 117727701, 'price': '5786.76000000', 'quantity': '0.03200500', 'buyer_order_id': 341831847, 'seller_order_id': 341831876, 'trade_time': 1556876873648, 'is_market_maker': True, 'ignore': True, 'unicorn_fied': ['binance', '0.1.0']}
```
Currently this module has no dependencies.

If you like the project, please [![star](https://s3.gifyu.com/images/stard237b3003af9f9a9.png)](https://github.com/oliver-zehentleitner/unicorn_fy/stargazers) it on 
[GitHub](https://github.com/oliver-zehentleitner/unicorn_fy)! 

## Supported Exchanges
### Websockets
- binance.com ([API specification](https://github.com/binance-exchange/binance-official-api-docs))
- binance.com-futures ([API specification](https://github.com/binance-exchange/binance-official-api-docs))
- binance.com-margin ([API specification](https://github.com/binance-exchange/binance-official-api-docs))
- binance.je ([API specification](https://github.com/binance-jersey/binance-official-api-docs/))
- binance.us ([API specification](https://github.com/binance-us/binance-official-api-docs))
- binance.org ([API specification](https://docs.binance.org/))

### REST
- none

## Installation and Upgrade
### A wheel of the latest release with PIP from [PyPI](https://pypi.org/project/unicorn-fy/)
`pip install unicorn-fy --upgrade`

### From source of the latest release with PIP from [Github](https://github.com/oliver-zehentleitner/unicorn_fy)

#### Linux, macOS, ...
Run in bash:

`pip install https://github.com/oliver-zehentleitner/unicorn_fy/archive/$(curl -s https://api.github.com/repos/oliver-zehentleitner/unicorn_fy/releases/latest | grep -oP '"tag_name": "\K(.*)(?=")').tar.gz --upgrade`

#### Windows
Use the below command with the version (such as 0.2.0) you determined [here](https://github.com/oliver-zehentleitner/unicorn_fy/releases/latest):

`pip install https://github.com/oliver-zehentleitner/unicorn_fy/archive/0.2.0.tar.gz --upgrade`

### From the latest source (dev-stage) with PIP from [Github](https://github.com/oliver-zehentleitner/unicorn_fy)
This is not a release version and can not be considered to be stable!

`pip install https://github.com/oliver-zehentleitner/unicorn_fy/tarball/master --upgrade`

## Documentation
- [General](https://oliver-zehentleitner.github.io/unicorn_fy)
- [Modules](https://oliver-zehentleitner.github.io/unicorn_fy/unicorn_fy.html)

## Source, Downloads, Examples, ...
[https://github.com/oliver-zehentleitner/unicorn_fy](https://github.com/oliver-zehentleitner/unicorn_fy)

## Change Log
[https://oliver-zehentleitner.github.io/unicorn_fy/CHANGELOG.html](https://oliver-zehentleitner.github.io/unicorn_fy/CHANGELOG.html)

## Wiki
[https://github.com/oliver-zehentleitner/unicorn_fy/wiki](https://github.com/oliver-zehentleitner/unicorn_fy/wiki)

## Social
- [https://t.me/unicorndevs](https://t.me/unicorndevs)
- [https://dev.binance.vision](https://dev.binance.vision)

## Receive Notifications
To receive notifications on available updates you can 
[![watch](https://s3.gifyu.com/images/github_watch.png)](https://github.com/oliver-zehentleitner/unicorn_fy/watchers) 
the repository on [GitHub](https://github.com/oliver-zehentleitner/unicorn_fy), write your 
[own script](https://github.com/oliver-zehentleitner/unicorn_fy/blob/master/example_version_of_this_package.py) 
with using `unicorn_fy.is_update_availabe()` or you use the 
[monitoring API service](https://github.com/oliver-zehentleitner/unicorn-binance-websocket-api/wiki/UNICORN-Monitoring-API-Service).

## How to report Bugs or suggest Improvements?
[List of planned features](https://github.com/oliver-zehentleitner/unicorn_fy/issues?q=is%3Aissue+is%3Aopen+label%3Aenhancement) - 
click ![thumbs-up](https://s3.gifyu.com/images/tu.png) if you need one of them or suggest a new feature!

Before you report a bug, [try the latest release](https://github.com/oliver-zehentleitner/unicorn_fy#installation-and-upgrade). 
If the issue still exists, provide the error trace, OS and python version and explain how to reproduce the error. 
A demo script is appreciated.

If you dont find an issue related to your topic, please open a new issue:
[https://github.com/oliver-zehentleitner/unicorn_fy/issues](https://github.com/oliver-zehentleitner/unicorn_fy/issues)

[Report a security bug!](https://github.com/oliver-zehentleitner/unicorn_fy/security/policy)

## Contributing
[unicorn_fy](https://github.com/oliver-zehentleitner/unicorn_fy) is an open 
source project which welcomes contributions which can be anything from simple documentation fixes to new features. To 
contribute follow 
[this guide](https://github.com/oliver-zehentleitner/unicorn_fy/blob/master/CONTRIBUTING.md).
 
### Contributors
[![Contributors](https://contributors-img.web.app/image?repo=oliver-zehentleitner/unicorn_fy)](https://github.com/oliver-zehentleitner/unicorn_fy/graphs/contributors)

We ![love](https://s3.gifyu.com/images/heartae002231c41d8a80.png) open source!

### Donate
Since you are probably a developer yourself, you will understand very well that the creation of open source software is 
not free - it requires technical knowledge, a lot of time and also financial expenditure.

If you would like to help me to dedicate my time and energy to this project, donations are very welcome.

[![Donate using Liberapay](https://liberapay.com/assets/widgets/donate.svg)](https://liberapay.com/oliver-zehentleitner/donate)

```
BTC: 39fS74fvcGnmEk8JUV8bG6P1wkdH29GtsA
DASH: XsRhBuPkXGF9WvifdpkVhTGSmVT4VcuQZ7
ETH: 0x1C15857Bf1E18D122dDd1E536705748aa529fc9C
LTC: LYNzHMFUbee3siyHvNCPaCjqXxjyq8YRGJ
XMR: 85dzsTRh6GRPGVSJoUbFDwAf9uwwAdim1HFpiGshLeKHgj2hVqKtYVPXMZvudioLsuLS1AegkUiQ12jwReRwWcFvF7kDAbF
ZEC: t1WvQMPJMriGWD9qkZGDdE9tTJaawvmsBie
```
## You need a Python Dev?
If you would like to [hire me](https://about.me/oliver-zehentleitner) for a Python project, you can book me through 
my company [LUCIT](https://www.lucit.co/desktop-and-server-apps.html).
