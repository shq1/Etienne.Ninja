---
title: "Linux basics for hackers"
tags: ["Sécurité 201"]
date: 2021-03-07T12:20:27-05:00
image: "cover.jpeg"
note: 8/10
Auteur: OccupyTheWeb
---

 
---
locate uses a database that is usually only updated once a day, so if you just created a file a few minutes or a few hours ago, it might not appear in this list until the next day.

*****

The ? wildcard is used to represent a single character, so a search for ?at would find hat, cat, and bat but not what, because at in this filename is preceded by two letters

*****

search for [c,b]at would match cat and bat but not hat or what

*****

asterisk (*), which matches any character(s) of any length, from none to an unlimited number of characters. A search for *at, for example, would find cat, hat, what, and bat.

*****

With less, you can not only scroll through a file at your leisure, but you can also filter it for terms

*****

If you press the forward slash (/) key, less will let you search for terms in the file

*****

iwconfig command to gather crucial information for wireless hacking such as the adapter’s IP address, its MAC address, what mode it’s in, and more

*****

ifconfig followed by the interface you want to reassign and the new IP address you want assigned to that interface

*****

To request an IP address from DHCP, simply call the DHCP server with the command dhclient

*****

apt-cache command to search the apt cache, or the place it stores the package names

*****

The remove command doesn’t remove the configuration files

*****

Linux automatically assigns all files and directories default permissions of 666 and 777, respectively. This means that, by default, you won’t be able to execute a file immediately after downloading it.

*****

Running the ps command with the options aux will show all processes running on the system for all users

*****

This is where the top command comes in handy because it displays the processes ordered by resources used, starting with the largest

*****

nice  -n -10 /bin/slowprocess This command would increment the nice value by -10, increasing its priority and allocating it more resources.

*****

The at command is a daemon—a background process—useful for scheduling a job to run once at some point in the future. The crond is more suited for scheduling tasks to occur every day, week, or month,

*****

make the changes permanent, you need to use the export command. This command will export the new value from your current environment (the bash shell) to the rest of the system

*****

If you want to delete this new variable, or any variable, use the unset command

*****

Lossy compression is very effective in reducing the size of files, but the integrity of the information is lost

*****

You can then extract those files from the tarball using the tar command with the -x (extract)

*****

In general, compress is the fastest, but the resultant files are larger; bzip2 is the slowest, but the resultant files are the smallest; and gzip falls somewhere in between

*****

The bs option allows you to determine the block size (the number of bytes read/written per block) of the data being copied. By default, it is set to 512 bytes, but it can be changed to speed up the process. Typically, this would be set to the sector size of the device, most often 4KB (4,096 bytes)

*****

general rule, internal hard drives are mounted at /mnt, and external USB devices such as flash drives and external USB hard drives are mounted at /media

*****

The filesystems that are mounted on a system are kept in a file at /etc/fstab (short for filesystem table)

*****

command df (for disk free) will provide us with basic information on any hard disks or mounted devices

*****

fsck command (short for filesystem check) checks the filesystem for errors and repairs the damage, if possible, or else puts the bad area into a bad blocks table to mark it as bad

*****

the rsyslog.conf file comes well documented with numerous comments explaining its use.

*****

delete the file and overwrite it several times, making it much harder to recover. Lucky for us, Linux has a built­in command, appropriately named shred, for just this purpose.

*****

shred will delete the file and overwrite it several times—by default, shred overwrites four times

*****

To disable all logging, the hacker could simply stop the rsyslog daemon

*****

the most widely used Linux SSH service is OpenSSH, which is installed on nearly every Linux distribution

*****

fork of the MySQL database software called “Maria” that is committed to keeping this software and its subsequent versions open source.

*****

what hops a packet might make between you and the destination, you can use the traceroute command

*****

tradeoff is that surfing via the Tor browser can be a lot slower;

*****

The websites that make up the dark web require anonymity, so they allow access only through the Tor browser, and they have addresses ending in .onion for their top­level domain (TLD)

*****

use more than one proxy, in a strategy known as a proxy chain

*****

tool called proxychains that you can set up to obscure your traffic

*****

proxychains defaults to using Tor if you don’t enter any proxies of your own

*****

the free proxies are likely selling your IP address and browsing history

*****

iwlist. For our purposes, we’ll use the scan action to see all the Wi­Fi APs in your area.

*****

Monitor mode is similar to promiscuous mode on wired network cards.

*****

When they reauthenticate, you can capture the hash of their password that is exchanged in the WPA2­PSK four­way handshake

*****

Bluetooth protocol stack called BlueZ that we’ll use to scan for Bluetooth signals.

*****

hciconfig This tool operates very similarly to ifconfig in Linux, but for Bluetooth devices.

*****

BlueZ provides the sdptool tool for browsing a device for the services it provides. It is also important to note that the device does not have to be in discovery mode to be scanned

*****

In some systems, to add a driver, you have to rebuild, compile, and reboot the entire kernel, but Linux has the capability of adding some modules to the kernel without going through that entire process. These modules are referred to as loadable kernel modules, or LKMs.

*****

uname -a

*****

cat command on the /proc/version

*****

sysctl command to tune kernel option

*****

lsmod command from the insmod suite to list the installed modules in the kernel

*****

learn more about any of the kernel modules, we can use the modinfo command

*****

A major advantage of using modprobe instead of insmod is that modprobe understands dependencies, options, and installation and removal procedures

*****

dmesg command, which prints out the message buffer from the kernel

*****

LKMs

*****

The cron daemon checks the cron table for which commands to run at specified time