---
description: 'Kotlin, MariaDB, automatic deployment и continuous integration'
---

# Technology stack

Application is written in strong typed language Kotlin. For database MariaDB is used, which is a fork of MySQL. Application follows layered architecture: there is service layer, DB layer, controller layer. Important parts of system are also covered with tests.

For HTML rendering template manager Freemaker is used, for API we use simple JSON. For each supported cryptocurrency custom clients are written, which use json/rpc api to gather data from nodes. Gathered data consist of addresses, transactions, specific blocks, transaction checks and etc.

For application compilation and bundling we use Gradle and Maven packages. For automatic deployment we use Docker: multiple containers are build via docker-compose. Deployment is done with continuous integration in TeamCity. Flow looks like this:

1. Build
2. Test
3. Deploy

Stage and review before deploy are currently absent.

