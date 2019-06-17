---
description: Which currencies do we support
---

# Currencies

### Currencies

At the moment of writing this article application supports 11 currencies  \(BTC, LTC, ETH, DASH, BCH, MDX, NANJ, ADA, NEO, DST, USDT\) and may be scaled easily to implement new currencies without core architecture changes.

CryptoHub supports different settings, which can be enabled/disabled for each currency separately.

* Amount of confirmations - this setting is used to set count of confirmations after which system will start parsing block
* Last block - for most of currencies represents last scanned block. It helps to detect if node is behind of actual state.
* Toggle: Do match addresses? - this option is needed to be enabled if we use node's API not only for querying specific addresses, but all transactions from given filter. For example: Bitcoin gives us only transactions attached to our addresses, while Ethereum gives all transactions.
* Withdrawal address - this field is address, which is used to transfer assets to public accounts for further users' withdrawals

There are several other parameters, which do not affect system, but are already added for further easy implementation.

![](https://lh5.googleusercontent.com/G5OMzDQIejSM-gnK3ve65zqSZUZM6RNXpVdUSvTK8yotvsU9_mi7fptKwigxHRSciv6IirZL4NJLW9ZJBADFH3WxHHiHAof6sfdr9MYWy_XWwdbgcPTBMUXFr64GQ5uAhHp1deXV)

### \*\*\*\*

