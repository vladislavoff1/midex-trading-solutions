---
description: 'Подключение к Trading Engine: FIX, Rest, WebSocket, Binary Protocol.'
---

# Gateways

![&#x421;&#x445;&#x435;&#x43C;&#x430; &#x440;&#x430;&#x431;&#x43E;&#x442;&#x44B; &#x448;&#x43B;&#x44E;&#x437;&#x43E;&#x432; &#x43F;&#x43E;&#x434;&#x43A;&#x43B;&#x44E;&#x447;&#x435;&#x43D;&#x438;&#x44F; &#x43A; Trading Engine](https://lh6.googleusercontent.com/kMzv-z7SNRzVSTD6j9tbqQ0VmUjfPerG3LHMyQV9jHAxpihAXjvIx-MdPnIRtaVEFgFafy-RxUdGg0QcDPI6zZ11J0bnesOxFUUF1O0E-H1rLPibcdKz-HWcSKvVXrMU9ODL7jZW)

## FIX ****

Fix Gateway делится на две части. Одна часть \(Connector\) контролирует TCP соединения и отвечает за fix-recovery \(пересылка старых сообщений клиенту\), другая \(Handler\) обрабатывает сообщения .

Connector и Handler могут общаться по IPC, если они на одной машине, или по UDP, если запущены на разных. Протокол общения написанный поверх UDP дает те же гарантии, что TCP, но работает быстрее. Этот же протокол используется для связи всех сервисов биржи, которые находятся на разных машинах.

Одна связка Connector + Handler по нашим тестам обрабатывает примерно 300 000 Fix-сообщений \(NewOrderSingle\) в секунду. Во время теста fix сообщение декодируется, конвертируется во внутренний протокол биржи и отправляется в ядро биржи. 

В зависимости от нагрузок, можно добавлять больше экземпляров Engine или больше экземпляров Library.

## **Rest**

## **Web Socket**

## **Binary Protocol**

