---
description: What are our result and which technologies do we use
---

# Architecture overview

## So what are our results like

**Over 5 millions of transactions per seconds may be processed.** Transaction is placing or cancelling order, registration or deposit to exchange account.

**Over 99.9% transactions are proceed faster than 100 microseconds.**

**Throughput of FIX Gateway is over 300 thousands requests per second.** This part scales well - if one gateway isn't enough to process all requests, another may be launched on a different server.

{% hint style="success" %}
Midex exchange proceeded over 16.6 millions of orders in 2 years of work. New trading engine replayed all history of exchange in just 3 second
{% endhint %}

{% hint style="info" %}
**Coinbase** exchange has around **30 deals per minute** at the moment of writing. New Trading Engine proceeds 5 millions events **per second**
{% endhint %}

## Which technologies do we use

### Kotlin, Java

Trading engine is written in Kotlin. Some codebase, which is focused on messages encoding is generated in Java.

### Event Sourcing

We keep all actions and events users produces, not the final state.

### No Databases

We dropped databases from our technology stack and writing all events into hard drive. **It is much faster and more reliable.**

### Aeron 

It is library for inter processes messaging, which also supports inter server communication.

### CQRS

We only read data from local cache for each gateway. Core of trading engine accepts only requests which change data.

## Business logic

Trading Engine core works on 1 thread, which leads to simpler code, lack of hard and unreliable multithread algorithms and context switching. **All this enables to write clean and simple code for business logic.**

In core of business logic we also use Event Sourcing. Business logic receives commands and returns events. I**t makes business logic easy to test** as well - we send commands and check, that right events are returned.

For Matching Engine we developed additional testing system. Tests are written in **markdown** format. Here are some pros of such tests:

* test is descriptive itself; analogue in kotlin or java would be harder to understand
* test can be written with business analysts
* test can be exported to html or pdf, which is good and descriptive documentation for exchange

And here is example of such test:

```text
Limit Order Test Case - Test 11
===============================

Add offer limit msg with existing bid price. Match

Initial state
-------------
| Order    | Type     | MES      | Time     | StopPx   | Size     | Price    | Size     | StopPx   | Time     | MES      | Type     | Order    |
| -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- |
| 3        | LIMIT    |          | 11:10    |          | 200      | 50.0     |          |          |          |          |          |          |
| 2        | LIMIT    |          | 11:00    |          | 200      | 80.0     |          |          |          |          |          |          |
| 1        | LIMIT    |          | 10:00    |          | 500      | 100.0    |          |          |          |          |          |          |

Aggressive Order
----------------
| Order    | Type     | MES      | Time     | StopPx   | Size     | Price    | Size     | StopPx   | Time     | MES      | Type     | Order    |
| -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- |
|          |          |          |          |          |          | 80.0     | 1000     |          | 12:00    |          | LIMIT    | 4        |

Final State
-----------
| Order    | Type     | MES      | Time     | StopPx   | Size     | Price    | Size     | StopPx   | Time     | MES      | Type     | Order    |
| -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- |
| 3        | LIMIT    |          | 11:10    |          | 200      | 50.0     |          |          |          |          |          |          |
|          |          |          |          |          |          | 80.0     | 300      |          | 12:00    |          | LIMIT    | 4        |

Trades
------
| TradeId  | Price    | Size     |
| -------- | -------- | -------- |
| 1        | 100.0    | 500      |
| 2        | 80.0     | 200      |

```



