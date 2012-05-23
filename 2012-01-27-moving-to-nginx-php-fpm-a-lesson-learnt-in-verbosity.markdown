---
date: '2012-01-27 14:04:10'
layout: post
slug: moving-to-nginx-php-fpm-a-lesson-learnt-in-verbosity
status: publish
title: 'Moving to nginx + php-fpm : A lesson learnt in verbosity'
wordpress_id: '1171'
categories:
- Site news
tags:
- apache
- derp
- memcached
- nginx
- php-fpm
- VirtualHost
- webserver
---

So yesterday I decided to move my web server from a typical LAMP setup with Memcached to a nginx + php-fpm setup. This in of itself is a rather simple task, I have already moved another site of mine to the same setup. But I ran into some issues while I was moving.

The issue was that my VirtualHost for this site wasn't working, it decided to redirect to my web root (which resulted in a 503 Forbidden of course since there wasn't anything there).



The error message:

{% codeblock %}2012/01/26 21:56:06 [error] 6931#0: *16 directory index of "/var/www/" is forbidden, client: 2001:470:1f06:dd1::2, server: localhost, request: "GET / HTTP/1.1", host: "asininetech.com"{% endcodeblock %}

At first I thought maybe my VirtualHost configuration was wrong:
{% codeblock %}

upstream php {
server 127.0.0.1:9000;
}

server {
listen 80;
listen [::]:80;
root $SITEROOT;
server_name asininetech.com;
index index.php;

# Cloudflare
set_real_ip_from 204.93.240.0/24;
set_real_ip_from 204.93.177.0/24;
set_real_ip_from 199.27.128.0/21;
set_real_ip_from 173.245.48.0/20;
set_real_ip_from 103.22.200.0/22;
set_real_ip_from 141.101.64.0/18;
set_real_ip_from 108.162.192.0/18;
real_ip_header CF-Connecting-IP;

location = /favicon.ico {
log_not_found off;
access_log off;
}

location = /robots.txt {
allow all;
log_not_found off;
access_log off;
}
location / {
index index.php index.html index.htm;
try_files $uri $uri/ /index.php?$args;
}

location ~ \.php$ {
include fastcgi_params;
fastcgi_pass php;
fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
fastcgi_index index.php;
}

location ~* \.(js|css|png|jpg|jpeg|gif|ico)$ {
expires max;
log_not_found off;
}
}

{% endcodeblock %}

But this was the exact same configuration I was using for my other VirtualHost which was working just fine.

My next thought was that maybe the SQL file I imported the database from was corrupted. So I redid the dump and re-imported the database. Still no luck, and I was still getting the same error. The logs didn't tell me anything more.

Now I figured, if there wasn't anything wrong with nginx or MySQL, the last remaining issue was the WordPress files I restored from my backup. So I downloaded the latest tarball from the wordpress.org and replaced the files. Still no luck.

The next morning, when I woke up, I decided to try the standard LAMP setup again, and to no surprise, it wasn't working either. So I took a look at the Apache error.log and voila:

{% codeblock %}[Fri Jan 27 11:01:22 2012] [error] [client 99.*.*.*] PHP Fatal error: Class 'Memcache' not found in $SITEROOT/wp-content/plugins/wp-memcached-manager/wp-memcached-manager.php on line 11{% endcodeblock %}

*facedesk*

While I was moving the site over, I removed all the plugins that used Memcached (object-cache.php, batcache) EXCEPT for that specific one. Removed the plugin directory for WP Memcached Manager and the site worked fine.

Lesson learnt - VERBOSE ALL THE ERRORS!
