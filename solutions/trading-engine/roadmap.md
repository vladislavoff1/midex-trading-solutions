---
description: What we want to implement in nearby future
---

# Roadmap

## Snapshots

To avoid full events replay, exchange's state is saved once per day\(it is called snapshot\). Using this approach system will only need to replay events for last day. Snapshot of core's state is made one time per day in time of low loads, for example, at night.

## Improvements in Leader-Follower

For fault tolerance we use several instances of exchange simultaneously. If one of them goes down system automatically switched to another. After restarting of failed node its state is restored from snapshot and events after it. It usually takes several minutes to finish.

## Binary Gateway

We need to add binary protocol to Trading Engine to decrease latency and increase throughput.

## Taker Maker

We need to implement ability to create different commission for taker and maker orders in business logic.

Maker - order in order book. Increases exchange liquidity

Taker - order which matches with another order from order book. Lowers liquidity.

