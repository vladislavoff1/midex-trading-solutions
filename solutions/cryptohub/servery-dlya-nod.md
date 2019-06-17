---
description: 'How many nodes do we use, do we need extra nodes and what about monitoring'
---

# Nodes workflow

### **Clients we use**

* **Bitcoin** - we use official node bitcoin-core, which suits perfectly our needs.[https://github.com/bitcoin/bitcoin](https://github.com/bitcoin/bitcoin)
* **Ethereum** - this node is used for Midex tokens and NANJ. We used to use official client written in `go` language - `go-ethereum`, but this software turned out to be unstable. As result we use time-proven node from parity - [https://github.com/paritytech/parity-ethereum](https://github.com/paritytech/parity-ethereum)
* **Neo** - for NEO currency\(tokens aren't used in system\) we use official client without web interface - [https://github.com/neo-project/neo-cli](https://github.com/neo-project/neo-cli)
* **Destream** - for DST currency we use official client, which is stable, despite several troubles in mining nodes. [https://git.poka.website/destream-public/destream-blockchain](https://git.poka.website/destream-public/destream-blockchain)
* **ADA \(Cardano\)** - client for ADA currency, we use official client. There used to be memory leaks, but last 6 months node works fine according to monitoring. [https://github.com/input-output-hk/cardano-sl](https://github.com/input-output-hk/cardano-sl)
* **USDT** - we use OmniCore client, which is fork from bitcoin-core v13. It works well without web interface on Ubuntu. [https://github.com/OmniLayer/omnicore](https://github.com/OmniLayer/omnicore)

### Cryptocurrency nodes

Depending on the cryptocurrency, we may need either one node or two. Each node has a set of metrics in Zabbix monitoring, which allows you to learn about problems with nodes before users write about this in technical support. Many errors are localized in such a way that users do not even have time to notice these errors.

Two nodes may be needed for currencies like Bitcoin, Litecoin, Dash, Bitcoin Cash, Cardano, Tether, DeStream. This is necessary because the node is in itself a wallet and does not mix incoming payments with outgoing payments. There is a clear separation of incoming and outgoing wallet, which allows us not to lose incoming payments and minimise losses when the system is hacked.

However, there are nodes like Ethereum, Neo, Tron, in which the client itself does not contain an account with private keys, so one node is enough to run currencies on these nodes. But you need to keep in mind that the cryptocurrency software is quite unstable, so it is always best to reserve nodes and have at least one spare node in reserve. Spare nodes are not kept in the same place, but have a separate server where they will be deployed.

### **Node monitoring**

Each node has its own API, its own surprises in terms of stability and its own metrics for monitoring system performance. Almost on all virtual machines several metrics are present, such as free space check, RAM, processor load, and the simplest metric is whether the node process is running. The monitoring system works on Zabbix.

For the Bitcoin family, which includes Litecoin, Dash, Bitcoin cash, there are metrics that check how far the node is lagging behind, various block load charts are also built. Monitoring also considers whether there has been a change in blocks in the last half hour. Below is an example of a Bitcoin block download schedule.

![&#x422;&#x430;&#x43A;&#x43E;&#x439; &#x436;&#x435; &#x433;&#x440;&#x430;&#x444;&#x438;&#x43A; &#x43C;&#x43E;&#x436;&#x43D;&#x43E; &#x443;&#x432;&#x438;&#x434;&#x435;&#x442;&#x44C; &#x438; &#x434;&#x43B;&#x44F; ethereum:](https://lh6.googleusercontent.com/Y1ev7N_7Gk9I_4LU5GBApLg53hmAMvc50aBG0I6c7WjJlK7UMQCy4FJutyA9UrxRPS8DCmyIcpg2zhxZFH3oN7kU6iqKogQ0AV-UCxz-8IO7pF3y6f850XW6iAcYLwFHcuV4LCik)



![](https://lh6.googleusercontent.com/b9NC-S_d_ObpKcRO9POXZhmthYs5rY3JZwOMYD95wn2hS_4_piofeTgU4TTgE9Q9zS7QzNFQCTklE3MG0MrKQlwiF90rNOfnqzDMdCCwT24QsQHVFxkoXI8cmucFxrRQ5ReoTnhM)

We had a situation that the blockchain of one of the developing currencies stopped while mining. Thanks to our metrics that monitor the emergence of new blocks at different time intervals, we noticed this problem and informed the developers of these currencies.

Nobody keeps an open tab with the Zabbix panel of course, this is inconvenient and you can skip something. All important notifications are sent to the developers telegram channel and also duplicated by email.

![](https://lh5.googleusercontent.com/sgaTu_r08EgJvEt99YGgDtc14_NZXjLL0AdppvBKLIvnr8eNOYdNZlmvMU97YOwxDG1VALfpg98n1_RmDZpE7sU1Fr38d1tM0sJSd4fCmfLSpklozGQYXeA9JretmJEEiAeAf8ot)



\*\*\*\*

