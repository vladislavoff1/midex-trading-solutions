---
description: Tips for Java low latency applications
---

# Low-latency optimisations

### Thread amount

When designing application it is important to match active thread count with system's cores count. Some of thread will be [CPU-bound](https://en.wikipedia.org/wiki/CPU-bound), some of them will be [IO-bound](https://en.wikipedia.org/wiki/I/O_bound). IO-bound threads often block while waiting for data from network of while sending data to network. Most of their lifespan they spend waiting for something and don't use CPU much. CPU-bound threads do heavy calculations and operations, and they need all resources they may have. 

If CPU-bound threads count is higher, than cores count, one thread will run low, because he will be out of priority compared to other CPU-bound threads.

It is likely to have CPU with higher amount of cores for JVM applications. It is also important to remember about service threads of JVM itself when designing application.

### Thread Affinity

It is must-have to match important threads with cores and restrict system to move thread to other cores, and also restrict system to move core to other threads. So one core is only used by on attached thread. There may be multiple important threads, and all off them should be bound. It is good practice to leave some extra cores for other threads. Thread affinity is done with third-party libraries and set up in code. We use [OpenHFT/Java-Thread-Affinity](https://github.com/OpenHFT/Java-Thread-Affinity).

### Shared memory access

We try to minimise amount of threads which have access to shared memory, so its easier to manage all this multithreading, synchronisation and locking management.

### Lock-free

We use [lock-free algorithms and data structures.](https://ru.wikipedia.org/wiki/%D0%9D%D0%B5%D0%B1%D0%BB%D0%BE%D0%BA%D0%B8%D1%80%D1%83%D1%8E%D1%89%D0%B0%D1%8F_%D1%81%D0%B8%D0%BD%D1%85%D1%80%D0%BE%D0%BD%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F) Blocking increase latencies of system critically and cause OS context switch. 

In case of lock-free structures part of code will load CPU core fully. It's fine, just make sure that thread is bound to this code, otherwise OS will try to stop thread, park it and execute other thread on this core. 

### Hard drive IO

Data written to logs should be as neat as possible. In low-latency applications hard drive IO is the most expensive kind of operations. Logging should be done **asynchronously:** application must not wait for IO to finish to continue its work, otherwise thread is blocked, context switch and etc. All the problems we want to avoid.

### Garbage collecting

Снизить до минимума [количество мусора](https://habr.com/ru/post/436024/), которое производит приложение. Чем быстрее heap заполнится мусором, тем скорее запустится сборщик мусора. 

Хранить данные и объекты можно за пределами JVM heap в нативной памяти JVM процесса. Это делается либо с помощью недокументированного класса [Unsafe](https://www.baeldung.com/java-unsafe).

It is important to minimise garbage application produces. The faster heap is filled with garbage, the faster GC is called to free RAM, which causes to temporal latency increases. 

Data may be stored outside of JVM heap in native memory of JVM process. It is done using experimental [Unsafe](https://www.baeldung.com/java-unsafe) implementation. 

