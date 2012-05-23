---
date: '2010-07-24 17:40:49'
layout: post
slug: how-to-get-a-working-arch-linux-desktop-with-gnome
status: publish
title: How to get a working Arch Linux desktop with GNOME!
wordpress_id: '104'
categories:
- Linux
- Tech
- Unasinine stuff
tags:
- Arch Linux
- desktop
- GNOME
- GUI
- linux
- open source
- operating systems
- OS
---

These are the steps I followed to get a working Arch Linux desktop with the GNOME desktop environment:


# Arch setup starts here:




> Put the Arch Linux CD in to your CD-ROM desktop and restart.

After all the loading is done type in : /arch/setup

Setup your partitions, timezones. (I formatted my whole HDD)

Select proper packages.
(sudo, glib, ca-cert, gmp, gpm, iptables, libcap, libevent, libldap, libnl, librpcsecgss, libsasl, libtirpc, links)

Set root password.

Edit rc.conf, change hostname to whatever you want.

Setup GRUB, add vga=773 to end of kernel line. (edit grub.conf)

Reboot.

**DON'T boot off the disc.**

Login using root credentials.

Edit repo list - nano /etc/pacman.d/mirrorlist

Uncomment (remove # symbols before URLS) all US repos except first one.

run pacman -Syu

reboot

run pacman -Syu again.

adduser whateverusernameyouwant
setup password.
Add to groups - audio, optical

Add username to sudoers list,
EDITOR=nano visudo
Basically copy the line for root except put your username in there.

Logout, and log back into your normal user.

sudo pacman -S xorg alsa-utils

Edit rc.conf
sudo nano /etc/rc.conf
Add hal, alsa to DAEMONS list.

sudo pacman -S gnome gnome-extra gnome-system-tools gksu

sudo pacman -S fam

Edit rc.conf again.
Add gdm (fam if not there) to DAEMONS list.

sudo pacman -S nvidia (If you have the ATI drivers consult [Arch Wiki](http://wiki.archlinux.org/index.php/Main_Page))
run nvidia-xconfig

Reboot!
Enjoy! :D


I recommend you try this in a virtual machine first using VirtualBox/VMWare. So if anything goes wrong, you'll know before hand.

For more and more help visit the Arch Wiki here - [http://wiki.archlinux.org/index.php/Main_Page ](http://wiki.archlinux.org/index.php/Main_Page )(P.S - greatest documentation ever!)

Alternatively, you can visit either #twil or #asininetech or #archlinux on irc.freenode.net for help.

I realize this is not a very thorough guide, but I think most people should be able to figure it out.
