# Just Linux Stuffs
  
## Table of Contents
* [Swap Memory](#Swap-Memory)  
* [Swappiness](#Swappiness)
* [Configuration file](#configuration-file)
	* [.desktop-file](#.desktop-file)
		* [desktop-file-example](#Postman-Example)

  
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

## Configuration file

In Linux, configuration files are files that contain settings and parameters used to configure the behavior of various system components, applications, and services. These files are typically plain text files that can be edited with a text editor and stored in specific directories or locations on the system.

Configuration files are used by the system and applications to customize and fine-tune their behavior to suit the needs of the user. They can be used to set options like network settings, user preferences, system settings, and more.

Some common places where configuration files are located in Linux include:

* /etc: This directory contains system-wide configuration files that are used by the operating system and various system components.

* /usr/share: This directory contains configuration files that are shared among different applications and packages installed on the system.

* /home/username: This directory contains user-specific configuration files that are used to customize the behavior of applications and system settings for individual users.

Configuration files can be edited using a text editor or via a command-line interface using utilities like sed or awk. It is important to be careful when editing configuration files, as errors can cause problems with the system or applications. It is recommended to make a backup of a configuration file before making any changes.

### .desktop file
A .desktop file in Linux is a configuration file that is used to create shortcuts to applications, files, or folders in a graphical user interface (GUI). It contains metadata such as the application name, icon, command to launch the application, and other properties that are used by the desktop environment or window manager to display and launch the associated application.

When you click on an icon or menu entry in a desktop environment like GNOME or KDE, the desktop environment reads the .desktop file associated with that entry and uses the information in the file to launch the associated application.

The .desktop file is typically stored in the /usr/share/applications or ~/.local/share/applications directory, and it uses the Desktop Entry Specification to define the properties of the desktop entry. This allows different desktop environments and window managers to display and launch applications consistently, regardless of the underlying technology used to create them.

### Postman Example:

```sh
[Desktop Entry]
Encoding=UTF-8
Name=Postman
Exec=/home/laxman/Apps/Postman/app/Postman #location to executable 
Icon=/home/laxman/Apps/Postman/app/resources/app/assets/icon.png #location to icon
Terminal=false
Type=Application
Categories=Development;

```
