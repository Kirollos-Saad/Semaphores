# Producer-consumer semaphore

This is a multi-threaded simulation program implemented in C using pthreads and semaphores. The program illustrates the use of semaphores in a producer-consumer scenario where multiple producer threads (counters) increment a shared counter, a monitor thread (producer) reads the counter value and enqueues messages into a buffer, and a collector thread (consumer) dequeues messages from the buffer.

## Problem Statement

Write a C program to solve the following synchronization problem using
POSIX and “semaphore.h” libraries.
N mCounter threads count independent incoming messages in a system and another thread
mMonitor gets the count of threads at time intervals of size t1, and then resets the counter to
0. The mMonitor then places this value in a buffer of size b, and a mCollector thread reads
the values from the buffer.
Any thread will have to wait if the counter is being locked by any other thread. Also, the
mMonitor and mCollector threads will not be able to access the buffer at the same time or to
add another entry if the buffer is full.
Assume that the messages come randomly to the system, this can be realized if the mCounter
threads sleep for random times, and their activation (sleep time ends) corresponds to an email
arrival. Similarly, the mMonitor and mCollector will be activated at random time intervals.


## Features

- **Producer Threads (Counters):** Multiple threads simulate message reception and increment a shared counter.
- **Monitor Thread (Producer):** Monitors the shared counter, reads its value, and enqueues messages into a buffer.
- **Collector Thread (Consumer):** Dequeues messages from the buffer.

## Requirements

- gcc compiler
- pthread library
- semaphores library

## Compilation

```bash
gcc -o semaphores_example semaphores_example.c -pthread
