---
description: >-
  The administration panel is used to customize the operation of the trading
  platform, moderate transactions and verify user data and their operations upon
  requests
---

# Administration

## Search

Search is performed by user ID and e-mail

## User page

Serves for checking and moderating user data. It has the following tabs

### Overview

![User overview](../../.gitbook/assets/image%20%287%29.png)

The following data is presented on this tab:

* Username
* Email
* User phone 
* Registration date and time 
* Date and time of account activation \(confirmation\) 
* Date and time of last login

Moderation tools are presented in a separate block:

* Enable / disable two-factor authentication 
* User login lock 
* Blocking user deposits 
* Lock user pins 
* Blocking user translations 
* User billing block 
* Block sharing with other users
* Blocking the creation of MDX codes
* Blocking transfers between main and exchange accounts

A separate block presents the history of user logins:

![Authentication history](../../.gitbook/assets/image%20%2831%29.png)

The history table displays:Дата и время входа

* IP login 
* User Browser 
* User operating system

### Personal data

This page displays the data specified by the user during the verification procedure.

* Name
* Surname 
* Middle name 
* Date of Birth 
* Country of issue of passport 
* Passport Number Series 
* Date of issue of passport 
* Passport validity 
* User Address

Under the block with this, scans of user-submitted documents submitted for inspection are displayed.

### Referral program

This page shows how much the user earned using the referral program.

![Exmaple referral program statistics](../../.gitbook/assets/image.png)

It shows the balance of earnings in each currency, as well as how many registrations were made by his referral link at each of the three levels. The total income is displayed for each level separately.

The Payouts tab displays the history of crediting referral rewards to the user's main account.

### User Balances

![User page](../../.gitbook/assets/image%20%288%29.png)

User balances are shown in two tabs: Main and Trade. The table shows all currencies and balances for each. Displays the fact of blocking a separate currency account and the date the lock was completed. Blocking can be due to the cause of the Antifrod system, which is valid for all new additions for each fiat gateway.

### User operations

This page shows all the operations performed by the user.

### **Transfers**

![Transfer table data example](../../.gitbook/assets/image%20%2818%29.png)

The table shows who the user was during the operation \(the sender or recipient\) and the name of his counterparty, by clicking on which you can go to his page. The amount and currency of the transfer are indicated, as well as the date and time of the transfer. The last column shows the confirmation of the operation by e-mail.

### **Invoices**

The table shows who the user was during the operation \(the creator of the account or the payer\) and the name of his counterparty, by clicking on which you can go to his page. The amount and currency of the transfer are indicated, as well as the date and time of the transfer. The last column indicates the status of the operation \(set, paid, declined\)

### Exchanges with other users

![Exchanges history](../../.gitbook/assets/image%20%281%29.png)

This page shows when and with whom the exchange was made, how much, how much, in which currencies. The exchange status \(proposed, accepted, declined\) and the comment to the exchange that indicates the initiator of the exchange is indicated.

### **MDX-codes**

This page shows a list of all codes that the user created.

![Created codes page](../../.gitbook/assets/image%20%2812%29.png)

The table shows all the information on the codes created:Создатель кода

* Who activated the code \(if no data, the code is not activated yet\)
* Date of creation
* Activation date 
* Amount 
* Currency 
* The fact of confirmation of the operation by e-mail

### **Open user orders**

![Open user orders table](../../.gitbook/assets/image%20%2814%29.png)

The table shows all the information on the currently open user ordersID ордера

* Currency pair
* Operation \(buy or sell\) 
* Price 
* The volume that remained unfulfilled to date 
* How much is frozen on the stock account 
* Initial order volume 
* Order Creation Date

### **Deal history**

![User deals history](../../.gitbook/assets/image%20%2836%29.png)

Displays all information on ever completed deals.

* Transaction ID
* Currency pair 
* Type of operation \(buy or sell\)
* Price 
* Volume 
* Commission 
* Closing date

### Deposit history

Displays the user’s top-up history, which is displayed exactly the same as the history of all top-ups only with filtering by the desired user.

### Withdrawal history

Displays the user replenishment history, which is displayed in the same way as the history of all pins only with filtering by the desired user.

### Cryptocurrencies addresses

Displays all addresses generated for the user for each currency.

## Monitoring table

![Montoring table example](../../.gitbook/assets/image%20%2830%29.png)

The table serves for visual monitoring of the financial balance of the system, checking for compliance of all inputs with all conclusions, including commissions for each currency.

Fields are:

* Main
* Trade
* In orders
* Commission
* In MDX-codes
* Total virtual assets in the system
* Fees paid
* All deposits
* Deposit Commission
* All withdrawals
* Check Digit \(Difference deposit and withdrawal\)
* Withdrawal commission
* Bank - how much the user funds should be in the system. This number is verified with the real funds held by the exchange.

## Currency pair settings

![Currency pair settings page](../../.gitbook/assets/image%20%286%29.png)

In this section, the administrator can turn on or off any trading pair placed on the stock exchange, as well as set limits and charged commissions, which are automatically transmitted to the public part of the site and to the trading terminal.

## Trading statistics \(volume\)

![&#x41F;&#x440;&#x438;&#x43C;&#x435;&#x440; &#x441;&#x442;&#x430;&#x442;&#x438;&#x441;&#x442;&#x438;&#x43A;&#x438; &#x442;&#x43E;&#x440;&#x433;&#x43E;&#x432; &#x43F;&#x43E; &#x43F;&#x430;&#x440;&#x430;&#x43C;](../../.gitbook/assets/image%20%2827%29.png)

По каждой валютной паре можно узнать статистику за день, неделю или месяц. При этом отдельно показывается информация по каждой валюте в паре.

При необходимости можно переключить таблицу на режим показа торговых оборотов по каждой валюте суммируя по каждой паре в которой она участвует.

## Статистика заработка биржи

![Example page of exchange earnings statistics ](../../.gitbook/assets/image%20%2829%29.png)

On this screen, the administrator has access to information about how much the exchange has earned in what currency. Under earnings refers to earnings on commissions from such operations as:

* Exchange 
* Trades 
* Paid bills 
* User exchanges
* Deposits
* Withdrawals

The last column shows the total profit for each currency.

## Fiat / Crypto Deposit Gateways

Responsible for the commission and limits for the deposit and replenishment of cryptocurrency and Fiat accounts.

![Example settings](../../.gitbook/assets/image%20%2811%29.png)

Each gateway can be turned on and off. Set commission type \(fixed or percentage\) for input and output separately.

## List of account deposits

![example of a chronological list of deposits on BTC](../../.gitbook/assets/image%20%289%29.png)

The page of the list of deposits shows a table for each of the cryptocurrencies in which the following data is displayed in chronological order:

* User name and ID \(when clicking, go to the user card\) 
* Date of operation 
* Currency type Refill amount 
* Hash transaction \(when clicked, opens the page with the monitoring of the transaction\) 
* The fact of transfer to the user's balance

## List of withdrawals

![Example of withdrawals list](../../.gitbook/assets/image%20%2838%29.png)

Before the table it is shown how much money is currently expected to be withdrawn \(green block\). The blue block shows how much funds are on the wallet of the system designed for withdrawals, from which the withdrawals are made automatically.

The output list page shows a table for each of the cryptocurrencies in which the following data is displayed in chronological order:

* User name and ID \(when clicking, go to the user card\) 
* Date of operation 
* Currency type 
* Withdrawal amount 
* Hash transaction \(when clicked, opens the page with the monitoring of the transaction\) 
* The fact of completion of the withdrawal. When an application is more than a certain amount, it is frozen until the moderator manually approves it\)

![Example of withdrawal which isn&apos;t confirmed by email](../../.gitbook/assets/image%20%2815%29.png)

Transactions not confirmed by e-mail are marked with a corresponding badge.

## Service Wallets

For some cryptocurrencies, an additional source of funds is needed that provides transactions. For ETH and ERC20 tokens it is gas, and for USDT it is BTC. The balance of such wallets is displayed on this page so that the administrator can control and quickly replenish it.

## Creation of system administrators

A simple role system where for each administrator created you can enable access to all the above functions or block it.

## User data export

![Export creation window](../../.gitbook/assets/image%20%2823%29.png)

Allows you to create a file with upload in which users sorted by the parameters specified in the filter will be marked. Upload will be available for download in a separate list.

![Example of ready exported data](../../.gitbook/assets/image%20%2833%29.png)

Each upload has its own name. Administrators can create daily, weekly reports for themselves according to specified parameters.

## Planned downtime switch

The ability to translate the exchange in the development mode. When it is turned on, all users of the exchange will see a page informing them that technical work is being done.

