---
date: '2012-04-21 16:44:58'
layout: post
slug: the-world-of-vps
status: publish
title: The World of VPS
wordpress_id: '1305'
categories:
- Reviews
tags:
- amazon
- cloud
- ec2
- Leaseweb
- Linode
- prgmr
- VPS
---

This will be a bunch of small reviews of all the VPS services that I have used in the past few years. Some of the details are a bit hazy (especially if the service was bad) and mostly put together from Paypal invoices so here goes _something._

<!-- more -->

(In chronological order)

**[Fastsh.it](http://fastsh.it/) (now merged with Bytesized Hosting)
**

This was my first real virtual private server. Excited with the prospects of a remote server with root access I go to install Apache, only to find out the repo URLs in the sources.list are broken. After finding the fix in their forums, I proceeded to install the software I needed. The server itself worked decently, except for server.lu having some annoying outages that resulted in complete loss of connectivity. I stayed with these guys for a month.

**[Omegabox](http://www.omegabox.me/) **

Another server.lu reseller (at least for the 100mbit VPS plan I used). No issues with the VPS itself, the connectivity issues previously experienced seem to have resolved.****

**[Amazon EC2](https://aws.amazon.com/ec2/)**

TingPing told me that there was a one year free trial so I signed up. The trial is for a micro instance with enough instance hours for every month**. **You get a decent amount of bandwidth and 613MB of RAM (a weird amount). The CPU is heavily throttled but is very usable for simple web hosting and running a IRC server.****

**[Prgmr](http://prgmr.com/xen/)**

Probably one of the best providers out there. I mean look at the tagline - _"We don't assume you are stupid."_ After initial payment, they ask you for a SSH key so they can give you out-of-band access to your VPS. Reverse DNS is available via request and you set up IPv6 connectivity yourself. A few downsides - they seem to be a pretty small team so tickets take a bit to get replies but on the flip side I only had to contact support for the initial set up. I only had a single instance of downtime and that was really my fault (I didn't realize Apache's default settings were not very safe for a 512MB VPS and the OOM killer kicked in.)

Overall, a highly recommended provider with great prices.

**[Leaseweb](http://www.leaseweb.com/en/cloud-hosting)**

Leaseweb probably has some of the best connectivity among the European providers**. **I had some issues with the VPS randomly rebooting (which is particularly annoying if you run a IRC server link on it). Technical support told me that was their automatic system for moving VMs when the host machine had issues**.

** [Linode](http://www.linode.com/?r=eb502ec47e3acaa700d98c0bc94a44453f958520)**

This is my current provider. If you know anything about VPSes, you have probably heard about Linode. I currently have 2 Linode 512 instances, both are running perfectly with no issues except for the occasional latency issues. They also have full IPv6 support with reverse DNS (both for IPv4 and v6), six different DC locations, DNS Manager for your domains and amazing customer service. Oh, and an amazing [wiki](http://library.linode.com).

**Overall conclusions**

The VPS industry is cutthroat one and it is wise to be careful. Remember, the age old adages - "You get what you pay for" and "If it looks too good to be true, it probably is".




