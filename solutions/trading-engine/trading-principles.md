---
description: Order types and how to implement new features
---

# Core of trading

## **Order types**

### **Limit**

Limit order is an order for buying or selling some assets for specified price or higher if available.

For example: if current market price is equal 250 and I want to buy for price lower than 249, I place limit BUY order with price 249. When market price will reach 249 and there will be match, limit order will be executed with price of 249.

### **Market**

Market order is an order which executes immediately with current base price. 

Market orders are usually used when execution time has higher priority than buy/sell price.

### **Stop**

Stop order is an order, which will execute as market order, when market will reach target stop price.

![Buy STOP &#x438;&#x441;&#x43F;&#x43E;&#x43B;&#x43D;&#x438;&#x442;&#x441;&#x44F;, &#x435;&#x441;&#x43B;&#x438; &#x446;&#x435;&#x43D;&#x430; &#x43F;&#x43E;&#x432;&#x44B;&#x441;&#x438;&#x442;&#x441;&#x44F; &#x434;&#x43E; &#x443;&#x441;&#x442;&#x430;&#x43D;&#x43E;&#x432;&#x43B;&#x435;&#x43D;&#x43D;&#x43E;&#x439;. Sell STOP &#x2014;&#xA0;&#x435;&#x441;&#x43B;&#x438; &#x43F;&#x43E;&#x43D;&#x438;&#x437;&#x438;&#x442;&#x441;&#x44F;.](../../.gitbook/assets/stop-orders.png)

Stop order for buy executes when market price lowers to a target price.                                                        Stop order for sell executes when market price rises to a target price.

Stop orders are used to avoid losses or securing profit.

### **Stop Limit**

Stop-limit order is an order which executes as limit when market reaches set stop price.

## Order execution policy

When order is being placed you can set up Time in Force - order execution policy. Default Time in Force of any order is Good Til Canceled.

**Good Till Cancelled \(GTC\)**

Order works unless is matched or cancelled. It best suits for long-term investor, who is ready to wait until asset price reaches wanted amount. Sometimes traders may wait for their order to execute with wanted price for some days or even weeks.

There are several risks though, such as execution in unwanted moments, such as short price grow or temporal volatility. Next price fall may lead trader to a loss.

**Fill or Kill \(FOK\)** 

Order executed immediately and fully with set price or cancels.

This policy is used to guarantee that order is executed at static price.

It can be popular on fast-growing markets, when traders want to be sure in good profits of deal.

**Immediate or Cancel \(IOC\)**

Order is executed immediately, unfulfilled part is cancelled.

Investors use IOC orders for big orders for a set price.



