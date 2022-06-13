# Awesome Low Latency

Low latency programming is increasingly important across a variety of use cases. Still, many of the tips and tricks of low latency are only part of developer folklore.
This document attempts to codify that knowledge for people to (re)discover the art of low-latency programming.

## Patterns

### Principles

* Colocating compute and data.
* Partition data to avoid sharing (and therefore synchronization).
* Make shared data structures read-only (when possible).
* Maximise cache hit rate.

### Memory

* Avoid dynamic memory management.
* Control memory access patterns.
* Avoid demand paging.
* Avoid as much work as possible (for example, avoid function call overhead by using inlining).

### Threads

* Avoid CPU intensive computation.
* Avoid context switching.
* Use wait-free data synchronization.
* Use busy-polling instead of wakeups.

### I/O

* Disable Nagle's algorithm.
* Use non-blocking I/O.

### Kernel-bypass

* Use kernel-bypass networking such as DPDK or XDP.
* Use hardware offload with accelerators and FPGA.

### System

* Know your underlying system (hardware, operating system, runtime, and so on)
* Configure your underlying system (for example, use preemptible kernel, watch out for bad device drivers).

### Latency measurements

* Avoid coordinated omission when measuring latency.

## Blogs

* [11 Best Practices for Low Latency Systems](https://bdarfler.medium.com/11-best-practices-for-low-latency-systems-a00fc6e0dfda) by Ben Darfler (2014).
* [Optimizing web servers for high throughput and low latency](https://dropbox.tech/infrastructure/optimizing-web-servers-for-high-throughput-and-low-latency) by Alexey Ivanov (2017).

## Publications

* [The Tail at Scale](https://cacm.acm.org/magazines/2013/2/160173-the-tail-at-scale/fulltext) by Jeffrey Dean and Luiz André Barroso (2013)
* [Tales of the Tail: Hardware, OS, and Application-level Sources of Tail Latency](https://drkp.net/papers/latency-socc14.pdf) by Jialin Li et al (2014)
* [Amdahl’s Law for Tail Latency](https://www.csl.cornell.edu/~delimitrou/papers/2018.cacm.amdahlsTail.pdf) by Christina Delimitrou and Christos Kozyrakis (2018)

## Conferences

* [P99 CONF](https://www.p99conf.io)
