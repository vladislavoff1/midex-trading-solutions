# Addresses generation

The generation of new addresses in the system differs: for some addresses, private keys are stored in the database in an encrypted form, and for some of them system has no access at all. It may be obvious in the comparison of two nodes - bitcoin and ethereum.

For bitcoin currency, the system uses the official bitcoin core client. This client has a wallet.dat file in which all private keys and public addresses are stored. Bitcoin core supports generating a large number of spare addresses using the keypoolrefill function, which allows us to generate a large number of keys into the file. Further, the wallet.dat file is encrypted and passed to the developers. After receiving this file, the developers see only public addresses. Further, Bitcoin core issues only public addresses when executing the corresponding command to receive an address. In fact, developers do not have access to wallet.dat private keys, only the owner of this wallet can spend all deposits.

![](https://lh5.googleusercontent.com/UMEgxXl4g4KMJE-B3WySP0vB9X1ySgrkVb9f2l7nsy6lZ1FI7s_1AV-XKc51rJT6AAHKMrsv76yyFui7EkjrVF0ifc-pnudB-EfDGB1qJ_Wxgk7P-nnLFgoWeVRgIWM1ktI450cK)

There are other ****nodes, such as ethereum, neo, and so on. These nodes do not use the wallet.dat file. When working with such nodes, the system generates a private key and a public address, the private key encrypts AES-256 with the key, and then saves it to the database. So the system works with nodes where it is impossible to generate an alternative wallet.dat file. The “access approved” column will be discussed later.

![](https://lh5.googleusercontent.com/HB8BvrMcJTePuaNPeYXK2nP7xU-seL_WIha8DsNmkgkRqm-ZUjv3Dd4JSucBJ2D0L-bhWrTJHjfIo6w9b-rLS9Xy-TZh6K7c3NVJJ5c6dTw3fp648hCXVDWeOQqIy4V-kCXlGfX8)

### \*\*\*\*

