---
date: '2011-10-31 08:51:54'
layout: post
slug: how-to-secure-a-ssh-server
status: publish
title: 'HOWTO: Secure a SSH server'
wordpress_id: '959'
categories:
- Howtos
tags:
- bruteforce
- bsd
- linux
- security
- SSH
- vim
- windows
---






If you manage a Linux server, chances are that you will want to control and check it remotely. This involves the use of SSH. This how-to will show you how to secure your SSH server in two different ways.



These are the steps I take to securing a new Linux server:



	
  1. Login as root.

	
  2. Create a new non-root account.

    adduser bob



	
  3. Give it sudo privileges using [visudo](http://man.cx/visudo)

    bob ALL=(ALL) ALL

Protip, visudo by default opens vim as your editor, you can use the editor of your choice by:

    $EDITOR=nano visudo



	
  4. Disable root login in /etc/ssh/sshd_config

    
    PermitRootLogin no




	
  5. From here you can go two routes, passwordless auth only (using keys) or using passwords + a bruteforce protection system.


**Passwordless authentication only**



	
  1. Disable password logins in /etc/ssh/sshd_config

    PasswordAuthentication no



	
  2. Now you need to generate OpenSSH keys on whatever machine you want to login from. Do this if on Linux:

    ssh-keygen -t rsa -b 4096

If on a Windows machine, you can use [puttygen](http://the.earth.li/%7Esgtatham/putty/latest/x86/puttygen.exe) to generate a OpenSSH key. [Screenshot](http://dl.dropbox.com/u/2888062/Screens/20111029162916834.png) . Make sure to use a strong passphrase.

	
  3. Now you need to put the public key in the authorized_keys file in $HOME/.ssh/authorized_keys on the host machine. On Linux, to get the pubkey of the SSH key you just generated go into $HOME/.ssh/
   {% codeblock %}
   cat id_rsa.pub
   {% endcodeblock %}
Copy and paste that into the authorized_keys file. In puttygen, the pubkey is displayed when the key is generated.

	
  4. Save the authorized_keys file. Restart SSH server, **but keep the SSH connection open.** This is to prevent a lockout in case of misconfiguration.

	
  5. Open another SSH connection and test using your new key, if all goes well, you should be asked for a username and the **passphrase for your SSH key**. If you are using putty, the procedure will be slightly different, use puttygen to save a private key (when you make your pubkey) and load that private key using the Auth option in putty.


**Password based route**



	
  1. Make sure you have a strong password for your user accounts.


	
  2. Install bruteforce protection software like [fail2ban](http://www.fail2ban.org/wiki/index.php/Main_Page)/[denyhosts](http://denyhosts.sourceforge.net/)/[sshguard](http://www.sshguard.net/). I use fail2ban on my servers, the default config is mostly sane, you may want to increase the bantime for SSH though. All of these softwares watch /var/log/auth.log so make sure your logging daemon is working properly.


**Note: You can still use key-based authentication at the same time if you want to.**

**Further iptables security (by foxwolfblood)**







You can add to the security by adding in other iptables rules, also if you can get access to this from your local network you may want to also have it listening on port 22 out of convenience. (wanport == your non-standard port)

    Port wanport Port 22

To make sure this can't be accessed from the WAN you would use (im going to use 192.168.1.0 as the example subnet)

    iptables -A INPUT -s 192.168.1.0/24 -p tcp --dport 22 -j ACCEPT; iptables -A INPUT -p tcp --dport wanport -j ACCEPT; iptables -A INPUT -p tcp --dport 22 -j DROP













