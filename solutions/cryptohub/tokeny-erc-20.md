---
description: How we save on commissions
---

# ERC-20 Tokens

We should also note the ERC-20 tokens that work on the Ethereum platform. There are no problems with replenishing wallets to tokens, however, these tokens must also be somehow sent to the owners of the exchange. But there is a problem: to apply the transfer method in the direction of a smart contract, you need to pay for the gas to complete the transaction.

First we thought of something like this:

1. If there are tokens on address, continue
2. If there is no ethereum on address, replenish balance with ethereum
3. Posting transfer request to smart contract to move tokens to a new address

However, this method is not very economically good: with each replenishment of the wallet with tokens, it would be necessary to replenish it with ether and then again make a request to the smart contract. To save money on commissions, a tricky and non-transparent method of withdrawing funds was introduced.

We added new accounts to system:

* Service deposit wallet from which a certain amount of ether is sent to addresses where there are target tokens
* Service transfer wallet, that calls the `transferFrom` method to transfer a token from one wallet to another \(for this operation you need to get a approval to the address using the `approve` method\)

The replenishment algorithm is like that:

1. If wallet receives tokens, we check whether `approve` has been made to the smart contract earlier
2. If there was no approve for the service transfer wallet, then the deposit wallet sends to the given address ether if there is not enough ether at this address
3. If the wallet has been replenished by ether and the `approve` method has not been called, then the transaction with the `approve` method is sent to the address of the smart contract and an approval is issued to perform the transactions from the service transfer wallet.
4. The service transfer wallet calls the `transferFrom` method and removes tokens from the top-up wallets.

В итоге мы имеем следующую картину: после первого пополнения кошелька токенами, сервисный кошелек deposit пополняет его eth, отправляет запрос approve в смарт-контракт, и затем сервисный кошелек transfer выводит все токены на новый кошелек. Далее при пополнении этого же адреса, сервисный кошелек transfer сам выведет токены.  


As a result, we have the following flow: after the first replenishment of the wallet with tokens, the service deposit wallet replenishes its ether balance, sends the `approve` request to the smart contract, and then the service transfer wallet withdraws all the tokens to the new wallet. Then on replenishment of this address, the service transfer wallet itself will withdraw tokens.

