---
date: '2012-05-04 12:33:25'
layout: post
slug: ipv6-adventures-wrt54gl-and-openwrt
status: publish
title: IPv6 adventures - WRT54GL and OpenWRT
wordpress_id: '1323'
categories:
- Howtos
- Linux
tags:
- IPv6
- Linksys
- networking
- OpenWRT
- WRT54GL
---

Yesterday foxwolfblood told me that his WRT54GS was capable of doing IPv6 (via tunnel) so I decided to put my WRT54GL to some use.

<!-- more -->

Things needed :



	
  * OpenWRT capable router

	
  * IPv6 tunnel (preferably from HE)




Flash your router with OpenWRT if you, haven't already done so.

According to the IPv6 essentials [page](http://wiki.openwrt.org/doc/howto/ipv6.essentials) on the OpenWRT wiki, you need to install these packages:

`opkg install kmod-ipv6 radvd ip kmod-ip6tables ip6tables`

Due to the limited amount of flash memory on my WRT54GL I left off the kmod-ip6tables and ip6tables packages. After those packages are installed, you need to install the 6in4 package.

`opkg update
opkg install 6in4`

Then, make sure IPv6 forwarding is enabled, edit /etc/sysctl.conf with this:

`net.ipv6.conf.all.forwarding=1`

Then, restart sysctl:

`/etc/init.d/sysctl restart`

Then, restart networking:

`/etc/init.d/network restart`

Wait a bit for networking to come back up. After that we need to configure 6in4, according to instructions from HE (example configurations: OpenWRT Backfire):
`
uci set network.henet=interface
uci set network.henet.proto=6in4
uci set network.henet.peeraddr=$IPV4ENDPOINT
uci set network.henet.ip6addr='$CLIENTIPV6ADDRESS'
uci set network.henet.tunnelid=$YOURTUNNELID
uci set network.henet.username=$USERNAME
uci set network.henet.password='YOUR_PASSWORD'
uci commit network
uci set firewall.@zone[1].network='wan henet'
uci commit firewall
ifup henet
/etc/init.d/firewall restart`

You also need to give the LAN interface a IPv6 address, like so (/etc/network):
`option 'ip6addr' '$FIRSTIPINROUTED64'`

Get the needed values from your tunnel example configuration. After those steps are done, IPv6 should be working **on the router**. Test it out by pinging a IPv6 capable server, like so:
{% codeblock %}
root@overlord:~# ping -6 -c 5 ipv6.google.com
PING ipv6.google.com (2607:f8b0:4004:800::1010): 56 data bytes
64 bytes from 2607:f8b0:4004:800::1010: seq=0 ttl=58 time=36.507 ms
64 bytes from 2607:f8b0:4004:800::1010: seq=1 ttl=58 time=35.575 ms
64 bytes from 2607:f8b0:4004:800::1010: seq=2 ttl=58 time=35.187 ms
64 bytes from 2607:f8b0:4004:800::1010: seq=3 ttl=58 time=36.053 ms
64 bytes from 2607:f8b0:4004:800::1010: seq=4 ttl=58 time=37.506 ms

--- ipv6.google.com ping statistics ---
5 packets transmitted, 5 packets received, 0% packet loss
round-trip min/avg/max = 35.187/36.165/37.506 ms
{% endcodeblock %}
Yay! The tunnel is working properly, but now we want IPv6 addresses for all our machines in the LAN. To do that, we need to configure radvd first. Empty out /etc/config/radvd (This is because for some reason UCI config for radvd fails) and then add this:

{% codeblock %}
config 'radvd'
        option 'config_file' '/etc/radvd.conf'
{% endcodeblock %}
Now, create a /etc/radvd.conf and put this in there (make sure to replace the prefix value with your /64 and the lan interface if yours is named differently):
{% codeblock %}
interface br-lan
{
        AdvSendAdvert on;
        prefix $YOURROUTED64
        {
                AdvOnLink on;
                AdvAutonomous on;
        };
};
{% endcodeblock %}
After you did that, start radvd like so:

`/etc/init.d/radvd start`

And you are good! Your IPv6 capable machines should have picked up a IPv6 address via autoconf.
**
More reading:**

	
  * [IPSec](http://ipv6.com/articles/security/IPsec.htm)

	
  * [radvd man page](http://linux.die.net/man/5/radvd.conf)

        
  * [ip6tables](https://www.sixxs.net/wiki/IPv6_Firewalling)

        
  * [History of IPv6 in Linux](http://tldp.org/HOWTO/Linux+IPv6-HOWTO/basic-history-ipv6-linux.html)


