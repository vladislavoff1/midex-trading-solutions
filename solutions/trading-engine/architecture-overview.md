---
description: Каких цифр добились. Какие технологии используем.
---

# Обзор архитектуры

## Каких цифр добились

**Скорость обработки транзакций — 5 млн/сек**. Транзакция — это постановка или отмена ордера, регистрация или пополнение биржевого счета. 

**99.9% запросов исполняются быстрее, чем за 100 мкс.**

**Пропускная способность** **FIX Gateway — 300 тыс/сек**. Если пропускной способности будет не хватать, можно будет поставить еще один FIX Gateway на другом сервере.

{% hint style="success" %}
За два года работы биржа Midex обработала 16.6 миллионов ордеров. Новый Trading Engine переиграл всю историю биржи Midex за 3 секунды. 
{% endhint %}

{% hint style="info" %}
На бирже **Coinbase** на паре ETH/BTC происходило около **30 сделок в минуту** в момент написания статьи. **Trading Engine** обрабатывает **5 миллионов** событий **в секунду**.
{% endhint %}

## Какие технологии используем

### Kotlin, Java

Trading Engine написан на Kotlin. Часть кода, связанного с кодированием сообщений генерируется в Java. 

### Event Sourcing

Храним все действия пользователей, а не конечное состояние.

### No Data Base

Мы отказались от баз данных и записываем все события в файлы на диск. Так быстрее и надежнее.

### Aeron 

Библиотека для общения между процессами и серверами.

### CQRS

Чтение данных из локального кеша для каждого шлюза. В ядро попадают только запросы, меняющие данные. 

## Бизнес логика

Ядро Trading Engine работает однопоточно, это позволяет писать простой код и отказаться от overhead’а многопоточных алгоритмов и переключения контекста. Из-за такой архитектуры **код бизнес логики — чистый**.

В ядре бизнес логики мы также используем Event Sourcing. Это значит, что бизнес логика получает команды и возвращает события на каждую команду. Из-за этого **бизнес-логику легко тестировать**: отправляем команды в бизнес логику, проверяем, что вернулись правильные события.

Для Matching Engine мы разработали дополнительную тестовую систему. Тесты для нее пишутся в формате Markdown. Преимущества таких тестов:

* тест наглядный, аналогичный тест на Kotlin или на Java читать сложнее
* тесты могут писать бизнес-аналитики
* тесты можно экспортировать в html или pdf — это всегда актуальная наглядная документация к бирже

Пример теста:

```text
Limit Order Test Case - Test 11
===============================

Add offer limit msg with existing bid price. Match

Initial state
-------------
| Order    | Type     | MES      | Time     | StopPx   | Size     | Price    | Size     | StopPx   | Time     | MES      | Type     | Order    |
| -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- |
| 3        | LIMIT    |          | 11:10    |          | 200      | 50.0     |          |          |          |          |          |          |
| 2        | LIMIT    |          | 11:00    |          | 200      | 80.0     |          |          |          |          |          |          |
| 1        | LIMIT    |          | 10:00    |          | 500      | 100.0    |          |          |          |          |          |          |

Aggressive Order
----------------
| Order    | Type     | MES      | Time     | StopPx   | Size     | Price    | Size     | StopPx   | Time     | MES      | Type     | Order    |
| -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- |
|          |          |          |          |          |          | 80.0     | 1000     |          | 12:00    |          | LIMIT    | 4        |

Final State
-----------
| Order    | Type     | MES      | Time     | StopPx   | Size     | Price    | Size     | StopPx   | Time     | MES      | Type     | Order    |
| -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- | -------- |
| 3        | LIMIT    |          | 11:10    |          | 200      | 50.0     |          |          |          |          |          |          |
|          |          |          |          |          |          | 80.0     | 300      |          | 12:00    |          | LIMIT    | 4        |

Trades
------
| TradeId  | Price    | Size     |
| -------- | -------- | -------- |
| 1        | 100.0    | 500      |
| 2        | 80.0     | 200      |

```



