---
published: true
title: Aptik - backup Ubuntu 19.04 system settings, packages, themes and more 
layout: post
category: Ubuntu
tags:
  - Linux
  - Ubuntu
  - Backup
  - Aptik
  - Clonezilla
description: Why Aptik is a great tool for backup up your Ubuntu system.
---
Aptik is a great tool to backup your Ubuntu system. Don't worry about partitions and problems anymore when changing devices and restoring systems.

_Author: Dennis Loska, 02.05.2019_

## Backing up Ubuntu

In the past I have been using Clonezilla to backup my Ubuntu installation, but I wasn't happy with it. It took too long, I was not being productive, and overall the need create a bootable device using the Clonezilla ISO was not fun for me. Furthermore restoring such a backup was equally problematic. Let's face it:

**I want to backup my files, not dealing with filesystem problems!**

That's why I decided to look for a backup solution, which would backup my systems settings, installed packages, data, themes etc.. I wanted to be able to work, while backing up my system in the background. So I started to search and stumbled upon [Aptik](https://github.com/teejee2008/aptik "Aptik").

> Aptik is a tool for migrating settings and data from one Linux installation to another. It can be used while re-installing the operating system, and when moving to next release of a Linux distribution.

Sounds great!

### Installation & Experience

Fortunately installing Aptik is **pretty easy:**

```shell
sudo apt-add-repository -y ppa:teejee2008/ppa
sudo apt-get update
sudo apt-get install aptik aptik-gtk
```

I already used Aptik for the past few months and successfully restored my Ubuntu system from my Laptop on another device, whilst upgrading the distribution and it worked really well. Now I just run _Aptik_ about once a week. Regular backups are important in my opinion.

![aptik backup.png]({{site.baseurl}}/images/aptik_backup.png)

## What exactly can you do with Aptik?

The way Aptik works is it backups basically all your options, settings, themes, wallpapers, the _home directory_ and so on. These are the key points to consider when **backing up & restoring** your system:

- can be used while re-installing the operating system or moving to next release of a Linux distribution.
- no encrypted backups, so encrypt your drive you backup to instead!
- restore operation should be run on a fresh Linux installation. 
- can be run on an existing system but this is not recommended
- supports Debian, Ubuntu, Fedora, Arch and their derivatives, but not all features are included ein every derivative
- only migrate between same architecture, e.g. 32bit to 32bit 

> Aptik should only be used to migrate between two installations of same distribution. For example, you can migrate from Fedora 24 to Fedora 25, or from Ubuntu 17.04 to Ubuntu 17.10, but not from Fedora to Ubuntu.

Aptik may not provide a backup of your whole partition, but for my use case as a simple system under which I develop things, I don't need to backup the whole partition. Besides that, restoring a Linux system is way easier by just reinstalling it and then using Aptik to restore the settings, than to restore it form Clonezilla, especially when you want to restore it on a **different device**. With Clonezilla you would end up messing around with the partitioning of your new device, which is not fun, if you try to setup a dual boot system.

You can still use Clonezilla off course, but I would use it to probably to backup the whole drive, and not only the partitions containing the Linux system.
