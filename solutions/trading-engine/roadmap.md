---
description: What we want to implement in nearby future
---

# Roadmap

## Snapshots

Для того, чтобы не проигрывать все события сначала, состояние биржи раз в день сохраняется \(создается снепшот\). Так события приходится проигрывать только за последний день. Снепшот ядра делается раз в сутки в момент пониженных нагрузок \(например, ночью\)

To avoid full events replay, exchange's state is saved once per day\(it is called snapshot\). Using this approach system will only need to replay events for last day. Snapshot of core's state is made one time per day in time of low loads, for example, at night.

## Обновление Leader-Follower

Для отказоустойчивости используется одновременно несколько ядер биржи. Если одно выходит из строя — система автоматически переключается на другое. При рестарте ядра оно восстанавливается со снепшота и проигрывает все события после него. Это обычно занимает несколько минут.

## Binary Gateway

Для уменьшения времени отклика и повышения пропускной способности нужно добавить бинарный протокол в Trading Engine. 

## Taker Maker

Добавить в логику биржи возможность создания разных комиссий для taker и maker ордеров.

Maker — ордер в книге ордеров. Повышает ликвидность биржи

Taker — ордер, который сталкивается с ордером из книги ордеров. Понижает ликвидность.

