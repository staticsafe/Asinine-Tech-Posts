---
date: '2010-07-04 15:42:31'
layout: post
slug: thoughts-on-arch-linux
status: publish
title: Thoughts on Arch Linux
wordpress_id: '83'
categories:
- Linux
- Tech
tags:
- Arch Linux
- distro
- foss
- installation
- linux
- oss
- thoughts
- twil
---

For the past few days I've been using the distro known as Arch Linux. Just in case you don't believe me here is proof:


[![Selection_003.png](http://asininetech.com/wp-content/uploads/2010/07/archproof.png)](http://asininetech.com/wp-content/uploads/2010/07/archproof.png)(Click to view clearly)


And yes, that's the Arch Logo.

**Installation**

This is the hardest part but due to YouTube videos made by platnumX, I knew what to do.Â I would say that this is definitely not a beginner's distro, people who have only used Ubuntu or have never used Linux at all.

With Arch Linux after the initial text based install where you setup partitions and install core packages (some additional ones are required as well), you boot into a good ol' command line. No GUI at all.

From there you update the system, and install the required packages to get a full GUI (xorg, alsa, gnome etc)

Had to edit a few conf files (especially rc.conf) to add daemons to start at bootup.

Also Canadians note - DON'T use the Canadian repos for packages, they suck. Use the US ones.

After all required packages were installed, I rebooted into a beautiful GDM screen.

**Hardware compatibility**

Most of my hardware worked just fine, except for the printer. Turned out that I had to install a specific package to get the OS to detect my printer.

**Documentation**

Arch has the best documentation ever. If you are a beginner, you have to read the Arch Wiki (wiki.archlinux.org). It's one of the best OS documentation I've ever seen. In fact, it's so good that a lot of the documentation will apply to any other distro you might encounter.

**Software repositories and package manager**

Arch has one of the best package management systems out there. It's called Pacman. One command allows you to update the whole system, and since Arch Linux is a rolling release distro it's very easy to stay up to date.

And yaourt allows you to easily auto-compile packages that are not available on the default repositories.

**Overall:**

In conclusion, I would say Arch is definitely a distro for you if you have some Linux knowledge and want to try something more challenging than Ubuntu.
