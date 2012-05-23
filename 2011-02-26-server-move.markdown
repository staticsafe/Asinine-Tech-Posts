---
date: '2011-02-26 21:24:24'
layout: post
slug: server-move
status: publish
title: Server Move
wordpress_id: '442'
categories:
- Site news
tags:
- amazon
- ec2
- server move
---

I am happy to say that this blog has been successfully moved to an [Amazon EC2](http://asininetech.com/2010/12/04/why-i-love-amazon-ec2/) server. And I daresay, it's running smoothly.

I would like to take this post to reiterate some small issues that I had while moving over the server:



	
  * Kept messing up the damn [Apache VirtualHost ](http://httpd.apache.org/docs/2.0/vhosts/examples.html)configuration

	
  * MySQL server randomly decides to die and wouldn't restart - changed binding options to fix it, and restarted EC2

	
  * Permalinks leading to a 404:
- Default WP permalink settings worked.
- Figured out mod_rewrite was not loaded with Apache
- Used a guide to figure out how to load it, which can be found [here](http://www.lavluda.com/2007/07/15/how-to-enable-mod_rewrite-in-apache22-debian/).

	
  * Wordpress kept asking me for FTP details when I wanted to update.
Solution: chown -R www-data: wp


Other than that the move was pretty straightforward.

**E-mail move**

**﻿**I should also mention that our e-mail services have now been moved to Google Apps.**
**

P.S - I'm still a little pissed as to the fact that I lost my 101 days uptime on the EC2, but honestly it was long due for a reboot after a bunch of kernel and system updates.
