# Just Linux Stuffs
  
## Table of Contents
* [Swap Memory](#Swap-Memory)  
  
## Swap Memory
In Linux, swap memory (also known as swap space or paging) is an area of the hard disk that is used to temporarily store data that cannot fit in the system's RAM (Random Access Memory). When a program or system process requires more memory than is available in RAM, the Linux kernel moves some of the data from RAM to the swap space, freeing up space in RAM for other processes.

Swap memory is usually used when the system is low on physical memory, or when a process requires more memory than is available in RAM. If the system runs out of both physical memory and swap memory, it may crash or become unresponsive.

The Linux kernel manages swap memory automatically, so there is no need for users to manually manage it. The amount of swap space available on a system can be configured during installation or later by adding or resizing a swap partition on the hard disk.

It is worth noting that using swap memory is much slower than using RAM because disk access is much slower than memory access. Therefore, it is generally recommended to have enough physical memory to meet the system's needs, rather than relying heavily on swap memory.

To check the current swap usage and availability on a Linux system, you can use the free command with the -h option:

```sh
free -h
```
The output shows the total amount of swap space available on the system, as well as how much of it is currently in use and how much is free.