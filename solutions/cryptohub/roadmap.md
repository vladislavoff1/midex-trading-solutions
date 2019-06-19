---
description: What is going to be implemented in nearby future
---

# Roadmap

## **Local addresses generation**

It is planned that the addresses and private keys to them will be generated locally on the customer’s / developers' machine. And only addresses will be downloaded to the server, without storing any keys to them. Coins will be unloaded from all addresses by launching the program on the local machine.

## **Balance monitoring**

It is planned to make a convenient interface for tracking the minimum amount on the balance sheets. The system will specify the address, the client, the minimum amount for notification. An example interface is shown below.

![](https://lh6.googleusercontent.com/pE1s_BXJdffBVeb_w59SgdElEhIaP3PNeK38gLdHpFcmlXJ6WUtoORbV5DYWBkCjOr0TVJm1R317YgvVRxe8_rGcDhrSOLS3fKZicHcBtoEF18V3rDfCZmmfk6BZH-wW8wKZGrMa)

## **Transaction broadcasting to mempool**

There is a problem when the mempool is full and transactions disappear from the send queue. We need to do the following:

1. Re-translate transactions into mempool if it is not mined
2. Understand the situation, see which transactions are mined already, and which still hang in mempool

