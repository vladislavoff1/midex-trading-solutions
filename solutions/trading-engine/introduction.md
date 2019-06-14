---
description: What is trading engine and what problems it must solve
---

# Introduction

## **What is Trading Engine**

#### **Performs** orders matching, keeps users' balances, counts commissions and spread money after deal.

### \*\*\*\*

![Trading Engine &#x438;&#x441;&#x43F;&#x43E;&#x43B;&#x43D;&#x44F;&#x435;&#x442; &#x43E;&#x440;&#x434;&#x435;&#x440;&#x430;](../../.gitbook/assets/trading_engine%20%281%29.png)

Trading engine serves for market makers, users and trading bots. This clients create load at more than 10000 operations in second.

**The most quantity of trading engine operations is money transfer transactions**. User places order, then his money move to exchange's account. When the order is matched and finished, money come back from exchange's account to user's.

Trading engine's functions are described more in "Trading fundamentals"

## What is Trading Engine should be like

### **1.** High throughput

Чтобы можно было торговать большому количеству торговых роботов. Каждая сделка — прибыль биржи. Так, повышая скорость биржи, мы повышаем возможное количество роботов, торгующих на ней и повышаем прибыльность.

With high throughput abilities of service more client it can serve. Each deal is beneficial for exchange, so the higher throughput is, the more trading bots may trade

### **2. Low and predictable latency**

Low latency is very important for high frequency trading bots. So if latency is higher comparing to other exchanges, exchange becomes harder to arbitrage. It is also important for all clients to be im same conditions for trading, meaning same latencies for matching orders.

### **3. Stability**

Каждая минута незапланированного простоя биржи — упущенные прибыль и репутация. Потерянные данные для биржи — крах.

При выходе биржи из строя или при выходе из строя целого датацентра \(например при пожаре\) биржа должна сохранить свои данные.

Each unplanned exchange downtime is lost profit and reputation. Lost data is a total disaster. When exchange or datacenter goes down unexpectedly it must save data. 

### **4. Flexibility to support different trade strategies**

The better orders can be configured, the more strategies users may use on exchange. Higher amount of trading bots may be launched and more profit exchange will get.

{% hint style="warning" %}
If exchange doesn't support stop orders, there is no way for "Stop loss and take profit" strategy, which is one of the main trading strategies for client without bots.
{% endhint %}

### **5. Support for common communication protocols**

Almost each fiat exchange support trading via FIX, which means almost each trading bot implementation support trading via FIX as well. Without FIX support there will be yet more limitations for trading bots to work on exchange. Having FIX supported enables trading bots to work flawlessly on Midex too.

