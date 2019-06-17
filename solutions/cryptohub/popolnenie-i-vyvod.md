# Deposit and withdrawal

### **Account deposit**

An important point in the system is the fact that the system is not aware of which user has an address. Depending on the type of cryptocurrency, one or another way of reading transactions from the blockchain is used.

For cryptocurrencies similar to bitcoin core, the system makes a request to the node via rpc api protocol and receives only transactions whose addresses are specified in the wallet.dat file. The system does not deal with the transfer of coins, as the system and the developers as a whole do not have access to the wallet.

For some currencies, there is another way to read transactions from the blockchain. For example, ethereum client: the system requests each block, receives all transactions, then looks at the out address of the transaction. If this address is in our database, the system saves data on the deposit. Also, the system, according to a certain rule and schedule, sends coins from these addresses to a cold wallet. Developers do not have access to this wallet.

Regardless of which currency is used, the system generates data with specific fields: amount, address, hash, number of confirmations. Also, the system has a special algorithm that checks how many confirmations each transaction has, and after each transaction notifies the exchange of changes in these transactions.

### **Account withdrawal**

The exchange also supports withdrawing cryptocurrency assets from user accounts to any external addresses. The exchange sends the system an internal transfer ID, the amount and the address where to send the cryptocurrency.

For bitcoin core wallets, we will definitely raise the second node, where we generate the wallet and have access to it. The owners of the exchange send coins from the cold wallets to this account. Thanks to this option, the risk of loss of cryptocurrency funds is reduced and the amount of possible damage is at a minimum.

For currencies where we use private keys, rather than wallet.dat, we also generate a private key and its address to the owners of the exchange. These accounts are used for user withdrawals.

After withdrawal, the system saves a transaction hash to the database and then sends the hash to the exchange. It takes less than 2 minutes to send a transaction to the hash exchange of a transaction.

Wallets balances are also connected to separate monitoring, and when the minimum amount remains on the wallets, or the total amount of withdrawals is greater than the output wallet balance remains, the system sends information about the shortage of funds to a special telegram chat for the exchange owners.  


