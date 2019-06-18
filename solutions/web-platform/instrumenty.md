---
description: >-
  The instruments serve the user for transactions with funds held in his
  accounts and for interacting with other users in order to gain financial
  benefits.
---

# Instruments

## Trading platform \(exchange\)

This is a trading terminal to work with which the user needs to have a positive balance on his exchange account.

![Terminal example](../../.gitbook/assets/image%20%285%29.png)

Currently, the following currency pairs are represented on the stock exchange \(90 pairs\):

MDX/BTC MDX/ETH MDX/USD MDX/EUR MDX/GBP MDX/JPY MDX/CNY MDX/BCH MDX/LTC MDX/DASH MDX/NANJ MDX/RUB ETH/BTC BTC/USD BTC/EUR BTC/GBP BTC/JPY BTC/CNY BCH/ETH ETH/USD ETH/EUR ETH/GBP ETH/JPY ETH/CNY BCH/BTC LTC/ETH BCH/USD BCH/EUR BCH/GBP BCH/JPY BCH/CNY LTC/BTC LTC/USD LTC/EUR LTC/GBP LTC/JPY LTC/CNY DASH/ETH DASH/BTC DASH/USD DASH/EUR DASH/GBP DASH/CNY NANJ/ETH NANJ/BTC NANJ/USD NANJ/EUR NANJ/GBP NANJ/JPY NANJ/CNY BTC/RUB ETH/RUB LTC/RUB DASH/RUB MDX/HKD BTC/HKD ETH/HKD BCH/HKD LTC/HKD DASH/HKD NANJ/HKD ADA/BTC ADA/ETH ADA/USD ADA/EUR ADA/GBP ADA/HKD ADA/JPY ADA/CNY MDX/ADA NEO/BTC NEO/ETH NEO/USD NEO/EUR NEO/GBP NEO/HKD NEO/JPY NEO/CNY MDX/NEO DST/BTC BTC/USDT ETH/USDT LTC/USDT MDX/USDT USDT/USD USDT/HKD TRX/BTC TRX/ETH TRX/USDT DST/ETH

Technical analysis tools are available to the user: TradingView.

Interface terminal features:

* View trading history for the selected currency pair
* View quotes from the percentage change per day 
* View your bidding history 
* View your open orders
* View available to the interaction orders placed by other users.
* Interactive chat with administrators or other users. Separate chat for each language

## Quotation aggregator

The user can monitor the quotations for the selected currency pair on any of the top cryptocurrency exchanges on one screen, analyze price changes, and also track it on a group chart.

![&#x43F;&#x440;&#x438;&#x43C;&#x435;&#x440; &#x433;&#x440;&#x443;&#x43F;&#x43F;&#x43E;&#x432;&#x43E;&#x433;&#x43E; &#x433;&#x440;&#x430;&#x444;&#x438;&#x43A;&#x430; &#x43F;&#x43E; 6 &#x431;&#x438;&#x440;&#x436;&#x430;&#x43C; &#x43F;&#x43E; &#x43F;&#x430;&#x440;&#x435; BTC/USD](../../.gitbook/assets/image%20%2826%29.png)

Quotations are updated automatically and provide the user with relevant information.

![Page of aggregator for BTC/USD pair](../../.gitbook/assets/image%20%2819%29.png)

## Account \(inner storage\)

Used to store user funds and transfer them somewhere. The wallet is protected by account protection:

* two-factor authentication
* encryption
* https 
* e-mail confirmation of all expenditure transactions 
* logging

![Login history](../../.gitbook/assets/image%20%2824%29.png)

For each cryptocurrency an unique replenishment address is generated, the CryptoHub service, which is also responsible for all external transactions, is responsible for the address generation process. Each wallet has its own unique ID, which is also the user ID.

![Page with already generated code](../../.gitbook/assets/image%20%2821%29.png)

The following gateways are connected and configured to work with fiat currencies:

![](../../.gitbook/assets/image%20%2822%29.png)

* WireTransfer \(created its own administration panel and work through a secure remote server\) 
* ZOTA Pay 
* Connectum

For additional security, there is a KYC procedure for a user account, which is currently implemented through integration with the SUM & Substance service, while we also have the technical ability to refuse this service and verify the user on our own.

## **MDX codes creation**

The user can create a unique digital code in which the necessary amount of funds in the selected currency will be encrypted.

![](../../.gitbook/assets/image%20%2820%29.png)

After the code is created, the user's balance is reduced by the amount indicated in the code, and the code becomes available for transfer to another user or for independent activation.

![](../../.gitbook/assets/image%20%2825%29.png)

When the code is activated, the user's balance is replenished by the amount encrypted in the code and the code is considered to be canceled and is no longer to be used.

## **Transfers to other users**

The user can send or receive a transfer within the system if there is the necessary balance in their accounts. To send a transfer, you must specify the recipient ID.

![](../../.gitbook/assets/image%20%282%29.png)

## Exchange with another user

The user has the opportunity to make an exchange with another user safely, without the risk of not receiving funds in return. To do this, one user sends exchange request to another user. At this moment, the amount offered for exchange is frozen in his account.

![Exchange example creation page](../../.gitbook/assets/image%20%2837%29.png)

The second user to whom the exchange offer is addressed may reject it or accept. In case of acceptance, the amount required for the exchange is deducted from his account, and the previously frozen funds of the first user are credited in exchange. The user can simultaneously have any number of offers for exchange.

![Exchange requests list](../../.gitbook/assets/image%20%2828%29.png)

## Payment and invoicing

Each user can create an invoice for payment and post it to another user by passing a unique link resulting from the creation of an invoice.

![Invoice creation modal](../../.gitbook/assets/image%20%2813%29.png)

![Bills list](../../.gitbook/assets/image%20%284%29.png)

The link opens a unique page with information about the invoice and can be accessed without authorization on the site. However, authorization is required for invoice payment. Each user can create any number of accounts.

![Bill overview](../../.gitbook/assets/image%20%2832%29.png)

## Referral program

We have developed a three-level referral program to stimulate the attraction of new users.

![](../../.gitbook/assets/image%20%2817%29.png)

**Referral program fetaures:**

* Creating referral links with your unique name and content 
* View statistics for each link 
* Tracking statistics on all three levels of the referral program 
* The calculation of the total income for the referral program in dollars 
* The ability to withdraw reward at the request of the user 
* Schedule user income for the week, month, year 
* Referral rewards payment history 

