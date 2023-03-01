# Just Linux Stuffs
  
## Table of Contents
* [Swap Memory](#Swap-Memory)  
* [Swappiness](#Swappiness)
  
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
  
## Swappiness
Swappiness is a Linux kernel parameter that controls the degree to which the system swaps out memory pages from RAM to the swap space. It is a value that ranges from 0 to 100, and it determines the kernel's tendency to move memory pages from RAM to swap.

A swappiness value of 0 means that the kernel will avoid swapping memory pages as much as possible and will instead try to keep them in RAM. On the other hand, a swappiness value of 100 means that the kernel will aggressively swap out memory pages from RAM to the swap space.

The default value of swappiness in most Linux distributions is usually set to 60, which strikes a balance between avoiding swapping too much and keeping enough free memory for running processes.

To view the current swappiness value on a Linux system, you can use the sysctl command with the vm.swappiness parameter:

```sh
sysctl vm.swappiness
vm.swappiness = 60
```
To change the swappiness value temporarily, you can use the sysctl command with the -w option followed by the new value:

```sh
sudo sysctl -w vm.swappiness=40
```

To make the change persistent across reboots, you can add the vm.swappiness parameter to the /etc/sysctl.conf configuration file and set it to the desired value:

```sh
vm.swappiness=40
```

It is worth noting that changing the swappiness value can have a significant impact on system performance, and it should only be done after carefully considering the system's memory usage and requirements.