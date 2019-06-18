---
description: >-
  For efficient operation of a liquidity management system, several robots are
  needed at once, operating in parallel and interacting not only with users, but
  also with each other
---

# Trading robot types

## **Volume robot \(order book filler\)**

Order books on the exchange must be filled with real orders, otherwise the user will not be able to buy a large amount of currency.

Placing large volume orders at close to market prices is dangerous. The price may change quickly and the robot will lose money.

Therefore, the robot divides the entire amount of currency allocated for placing in a order book and places orders at different distances from the market price. It is designed so that the further the price is from the market, the greater the volume at this price is set. The closest and furthest price from the market is customized.

The robot constantly monitors changes in the market price and rearranges orders that are not safe enough \(profitable\) for the robot.

To maintain user interest, the robot sometimes rearranges its orders even if the exchange rate does not change much. So the order book seems to be more “alive” and it becomes more interesting to trade on a currency pair.

When changing the liquidity allocated for trading, the robot smoothly changes the volume of the order book, imitating the actions of people, not robots.

## **Trading bot**

The robot puts two orders of the same volume, for sale and purchase, at the current rate. After cancels open orders if they remain. So the robot buys currency from users at a market or better price, or, if there are no such orders, it buys the currency from itself. This allows you to generate transactions on the exchange and creates activity on the exchange.

If there is no such robot, then the charts on the exchange will show low activity and new users will not trade on the exchange.

## Robot to maintain user interest

A robot places orders into a book at rates that are less favorable to themselves than a volume robot. After some time, the robot cancels them. This supports activity in the spread of the order book and increases the interest of users in the trade. The robot trades in a small volume, the frequency of transactions is regulated, this allows you to predict the costs of this robot.

