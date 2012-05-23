---
date: '2011-03-17 14:24:56'
layout: post
slug: more-legal-problems-for-android
status: publish
title: More Legal Problems for Android
wordpress_id: '604'
author: cafejunkie
categories:
- Asinine Corporations
- Asinine Stuff
- Linux
- News
tags:
- '2'
- '3'
- android
- apache
- applications
- apps
- bionic
- business
- C
- code
- copyleft
- copyright
- developrers
- foundation
- GNU
- google
- gpl
- header
- java
- kernel
- law
- lawyer
- library
- license
- linux
- open
- oracle
- OS
- price
- profit
- rules
- software
- source
- sun
---

By now everyone knows about Google's ongoing battle with Oracle over Java(tm) intellectual property. Since Android's source code is open source, it has increasingly become the target for media criticism. Recently, Ray Nimmer, a well-known copyright law professor noticed that there may be a new problem with Android. This problem relates to Android's use of Linux Kernel header files. This problem however, unlike the Oracle suit, has the potential to cause a lot of problems for application developers.


### What Google Did Now


As you may, or may not know, Android is built on top of the Linux kernel, an open source operating system kernel licensed under the GNU General Public License (GPLv2). The GPL is known as a "copyleft" license, which in short, means that one is free to share, modify and redistribute the software however that new modified version must also be licensed under the GPL in order to pass these same freedoms on to the next user.

Working with open source software requires careful attention to the legalities involved in using components from other projects. There are many open source licenses all with different license terms and conditions. Because Android is open source it is a very appealing platform for developers and manufacturers. A lot of developers even use components from the Android OS directly. This is wonderful, however it comes at a price.

Any for-profit business is going to want to be able to change the license terms of their own software in order for them to be able to charge license fees. Google understands that and so released Android the Apache Software License, a much more business friendly license than the GPL. You can probably already see what the problem is, but I'll explain further.


### Google Plays by it's own Rules


Prof. Nimmer's article raised a lot of valid questions about what Google has actually done, so I decided to take a look through the Android source myself. It turns out, Google used something called the "Bionic Library." This library is a C library that is used by application developers to access who need to access the core functions of the Linux operating system. In short, Google copied hundreds of files that were never actually meant to be used by developers, modified that code (in non-standard ways) and then dubbed the new files released under the Apache Software License, something which the GPL explicitly forbids.


### Why does all this Matter?


Now, I am not a lawyer and do not fully understand all of the legal repercussions that could potential happen here, but if there is one thing I do know it is my open sources licenses and what Google has done is 100% in violation of the GPL. The big problem in what Google has done is how it will affect developers, and any manufacturer who includes Android on their devices. Not only has Google taken a big risk here, but they by default brought everyone who ever had distributed Android into this fiasco. Should a copyright lawsuit arise out of this it could be devastating for the Android OS, and could potentially mean that 3rd party developers must release their applications under the GPL as well.

However, what is more frightening is what if Google is right in doing this? If Google is right, that would mean that our favorite tech giant has found a way to take Linux away from the open source community and privatize it. Can we really trust Google with that kind of power? I don't think so.
