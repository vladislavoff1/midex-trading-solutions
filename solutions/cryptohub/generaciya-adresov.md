# Генерация адресов

Генерация новых адресов в системе бывает разной: для каких-то адресов приватные ключи сохраняются в базу данных в зашифрованном виде, а к некоторым система вообще не имеет доступа. Далее это можно будет увидеть в сравнении двух нод - bitcoin и ethereum.

Для валюты bitcoin система использует официальный клиент bitcoin core. У данного клиента есть wallet.dat файл, в котором хранятся все приватные ключи и публичные адреса. У bitcoin core есть функция генерация большого количества запасных адресов с помощью функции keypoolrefill, что позволяет нам нагенерировать в файл большое количество ключей. Далее файл wallet.dat шифруется и передается разработчикам. Получив данный файл, разработчики видят только публичные адреса. Далее Bitcoin core выдает только публичные адреса при выполнении соответствующей команды на получение адреса. Фактически разработчики не имеют доступ к приватным ключам wallet.dat, все пополнения может тратить только владелец этого кошелька.

![](https://lh5.googleusercontent.com/UMEgxXl4g4KMJE-B3WySP0vB9X1ySgrkVb9f2l7nsy6lZ1FI7s_1AV-XKc51rJT6AAHKMrsv76yyFui7EkjrVF0ifc-pnudB-EfDGB1qJ_Wxgk7P-nnLFgoWeVRgIWM1ktI450cK)

Есть  ноды второго тип, такие как ethereum, neo и тд. В этих нодах не используется wallet.dat файл. При работе с такими нодами, система генерирует приватный ключ и публичный адрес, приватный ключ шифрует  AES-256 с ключом, и затем сохраняет в базу данных. Так система работаем с нодами, где нельзя сгенерировать альтернативный wallet.dat файл. Про графу “доступ одобрен” будет рассказано позже**.**

![](https://lh5.googleusercontent.com/HB8BvrMcJTePuaNPeYXK2nP7xU-seL_WIha8DsNmkgkRqm-ZUjv3Dd4JSucBJ2D0L-bhWrTJHjfIo6w9b-rLS9Xy-TZh6K7c3NVJJ5c6dTw3fp648hCXVDWeOQqIy4V-kCXlGfX8)

### \*\*\*\*

