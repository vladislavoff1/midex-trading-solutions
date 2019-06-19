---
description: No databases. Event Sourcing. Using files as long-term data store.
---

# Data storage

## Why no databases

Usually database keeps current state of an application. Here is example of database table with users' balances:

| user | balance |
| :--- | :--- |
| John | 100 USD |
| Bill | 10 USD |

Let's imagine such scenario: John wants to send `10 USD` to Bill. Trading Engine takes `10 USD` from John's account and adds `10 USD` to Bill's account. But server goes down between steps, and as a result John's account is already withdrawn, but Bill didn't receive his `10 USD`. Money is lost.

Modern databases support transactions to avoid such situations. Transaction is a very complex mechanism, which doesn't allow money to get lost even if server drops while money transferring. There is a cost though; complex transactions slow down application.

Assuming that almost each operation of Trading Engine is money transferring, each database operation with database should be wrapped in transaction, which leads to very slow operation speed. That's why we gave up on databases in Trading Engine.

## Event Sourcing

Instead of users' balances we keep users' events: deposit event, order creation. This approached is called Event Sourcing. We don't keep users' balances to hard drive. 

> We used to keep final state, but now we keep events:
>
> * Bill signed up
> * John signed up
> * John made a deposit for 100$
> * Bill made a deposit for 10$
> * John transferred 10$ to Bill

Even if server goes down while processing events, money won't lose.

## Events are written to hard drive

We don't need transactions or secondary indexes for safe events keeping. We don't need anything except consistent reading and appending of file. It increases speed of data storing compared to databases and simplifies replication. 

Since the events between modules are encoded using Simple Binary Encoding, it is not necessary to encode them a second time to save to disk.

Binary event buffer is mapped to file. When system restarts file is read to the same binary buffer.

## Storing current state to RAM

Current state of Trading Engine \(balances, open orders\) is only stored in RAM. If events changed user's balance we only change this balance in RAM. 

If server restarts, which includes clearing RAM, all stored events are replayed and there will be actual state in RAM.

\*\*\*\*



