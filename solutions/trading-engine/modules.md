---
description: What are Trading Engine's parts are and how they exchange data
---

# Modules

## **Definitions**

**Module** is an independent isolated part of Trading Engine. Module may be deployed on different server.

**Component** is an independent part of module. Components share memory between themselves inside module, and they also often work on one thread in module.

{% hint style="info" %}
Modules are designed such way that they may be deployed on different servers, but also may be run on same process. That allows Trading Engine to work even on laptop, which also helps in development and testing.
{% endhint %}

## Module list

**Application -** core module of Trading Engine. It implements core business logic: orders matching, commissions and currency pairs settings.

Application's components: 

* Matching Engine — orders matching
* Product Manager — addition and settings of currency pairs
* Account Store — keeps users' account state in each currency pair
* Hold Service — responsible for holding users' assets

**Archive** is responsive for data keeping and implemented in Aeron library.

**Gateway \(rest, websocket, fix and etc\) -** Trading Engines gateways. Each gateway is a different module. Gateway passes users' commands to Application module and broadcasts Application's events to users.

## Modules interaction

Data is exchanged between modules with **Aeron.** Aeron is a data transferring library, which works with unreliable media protocols, such as UDP and Infiniband. Aeron guarantees order of messages and messages' integrity, as well as message delivery.

**Messages are encoding with Simple Binary Encoding.** Messages encoded this way take less memory and are processed faster by system.

{% hint style="info" %}
Moscow exchange and LMAX use similar encoding for their messages.
{% endhint %}



