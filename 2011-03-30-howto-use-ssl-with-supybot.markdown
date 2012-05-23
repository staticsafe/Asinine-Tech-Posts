---
date: '2011-03-30 19:54:27'
layout: post
slug: howto-use-ssl-with-supybot
status: publish
title: 'HOWTO: Use SSL with Supybot'
wordpress_id: '636'
categories:
- Howtos
tags:
- bot
- howto
- IRC
- linux
- SSL
- supybot
- ubuntu
---

This howto will tell you how to use SSL to connect to IRC servers with [Supybot](https://sourceforge.net/projects/supybot/). As the name suggests, Supybot is  an IRC bot based on Python.

It is interesting to note that Supybot cannot use SSL to connect to IRC servers out of the box.

This is how you going around doing it:



	
  1. Install the twisted-names package from your distro's repos. (On Debian based distros, the package is called python-twisted-names)

	
  2. In your bot's conf file, change the value for this config variable "supybot.drivers.module" to Twisted.

	
  3. Change your network's server port to the specific SSL port for that server, which is usually 6697 (For Freenode, it's 7000)

	
  4. Restart your supybot.


Some issues:

	
  * The Twisted driver has an issue with AAAA records for domains, so if you are trying to connect to a server that has AAAA records, you will face issues. Relevant bug report can be found [here](http://twistedmatrix.com/trac/ticket/4212).

	
  * Freenode specific workaround - use chat.us.freenode.net as the server address. Thanks to this [post](http://pebkac.homelinux.net/2010/01/30/supybot-and-ssl-with-freenode/) for the solution. Should be considered a temp solution, as this sub-domain may get a AAAA name anytime.

	
  * Another workaround to this bug would be using an IP address instead of a domain name, but this is not the best idea as IP's may change.


I hope this guide helped you. Have fun with your Supybot!

P.S - As always, the authors hang out in #lounge on EntropyNet. Come join us!
