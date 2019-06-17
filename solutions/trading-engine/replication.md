---
description: Our Leader-Follower approach
---

# Replication

It is unsafe to keep all data on one server. If this server breaks, all data will be lost.

**All Trading Engine's data are stored simultaneously on several servers.** If one server breaks down, data won't be lost. ****

**Server which copies data is called replica.** Process of data copy on different servers is called replication.

**Количество реплик настраивается.** Обычно мы используем две реплики.

**Amount of replicas is customisable.** We usually use 2 replicas. 

The more replicas system has, the more reliable it is. The cost is speed, so there should be balance between reliability and performance in terms of replicas count.

## How replication is done

![Replication scheme](../../.gitbook/assets/leader_follower_architecture.png)

Replication is shown on scheme. Server with business logic may be run in 2 configurations: Leader or Follower.

* `Node` - server, which consists of 2 modules: `application` and `archive`, contains business logic and writes events to drive.
  * `Leader` — configuration when `node` may produce events
  * `Follower` — configuration when `node` subscribes to `Leader's` events
* `Application` — Trading Engine's business logic. [More on page «Modules»](modules.md#spisok-modulei).
* `Archive` — модуль сохранения данных, последовательно записывает поток сообщений на диск.
* `Archive` - data storage module, writes event stream consistently to drive

How does `node` work:

* `Application` processes command and generates events. `Follower` skips this stage
* Events are applied to inner state of `application` and publish
* Events from `application` are sent to `archive`
* `Archive` writes data to hard drive and publishes it

How does `node` work when starts:

* `Application` send request to `archive` to receive old events
* `Archive`reads events from drive and publishes them
* Events from `archive` are sent to `application`
* `Application`applies events to inner state



