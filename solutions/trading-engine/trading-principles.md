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

При постановке ордера можно настроить Time in Force — политику исполнения ордера.

Order 

По умолчанию Time in Force у ордеров — Good Til Canceled.

**Good Till Cancelled \(GTC\)**

Ордер действует до тех пор, пока сделка не будет выполнена или отменена. 

Подходит для долгосрочного инвестора, который готов подождать, пока актив достигнет желаемой цены. Иногда трейдеры могут совершить сделку по желаемой цене за несколько дней или даже недель.

Риски: выполнение заказов в неподходящие моменты, такие как краткий рост цен или временная волатильность. Последующее снижение цен может оставить трейдерам убытки.

**Fill or Kill \(FOK\)** 

Ордер немедленно и полностью исполняется по указанной цене или отменяется. 

Используется для гарантии того, что весь ордер выполняется по одной цене. 

Может быть популярным на быстроразвивающихся рынках, где трейдеры хотят убедиться, что они получают хорошую цену за сделку.

**Immediate or Cancel \(IOC\)**

Ордер немедленно исполняется, незаполненная часть отменяется.

Инвесторы используют заказы IOC для выполнения крупных заказов по определенной цене.



