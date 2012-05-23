---
date: '2011-08-11 17:26:31'
layout: post
slug: package-signing-coming-to-arch-linux-soon
status: publish
title: Package signing coming to Arch Linux soon
wordpress_id: '795'
categories:
- Linux
- News
- Tech
tags:
- Arch Linux
- linux
- news
- package management
- package signing
---

At long last, what many people have been asking for. It was one of the things mentioned often as a weakness for Arch Linux. Package signing is a security feature built into package management systems like apt to prevent package 'poisoning'. Package poisoning is a type of MITM attack where an attacker points your machine to his repo servers which contain malicious packages.

As far as I can find there has been no public incidents of package poisoning in Arch (feel free to correct me on this). In any case, some people will be happy to note that package signing is going to be built into [pacman](https://wiki.archlinux.org/index.php/Pacman) soon. This e-mail was posted on the arch-dev-public mailing list:


> 

>     
>     For the daring, pick your poison (by architecture):
>     
>     * pacman -U <a href="http://dev.archlinux.org/%7Edan/pacman-4.0.0rc1-1-i686.pkg.tar.gz">http://dev.archlinux.org/~dan/pacman-4.0.0rc1-1-i686.pkg.tar.gz</a>
>     * pacman -U <a href="http://dev.archlinux.org/%7Edan/pacman-4.0.0rc1-1-x86_64.pkg.tar.gz">http://dev.archlinux.org/~dan/pacman-4.0.0rc1-1-x86_64.pkg.tar.gz</a>
>     
>     Allan, Dave, and I (and probably a few others) run pacman-git on most
>     of our systems with no problems, so their should be no real shockers
>     or problems if you give this a spin. There are no database upgrades or
>     changes this time so downgrading later should work fine if truly
>     necessary.
>     
>     What we're looking for feedback on:
>     
>     * any build failures in makepkg you may see
>     * if you manage a custom repo, how does repo-add work for you
>     * does pacman behave as it did before
>     * if you want to sign packages, does the functionality in makepkg and
>     the documentation make sense
>     * same for signing repos- does it work for you
>     
>     What we know isn't there yet:
>     * translations
>     * a developer keyring (or keyring package)- if you delve into this,
>     you will need to look at pacman-key for now
>     * great error messages on verification failure, or ability to import
>     keys on the fly if it is unknown
>     
>     Note that we'd love testing even if you don't plan on touching any of
>     the new signing stuff- there were 500+ commits worth of changes in
>     this release, including a switch to curl as the download library, so
>     anything out of the ordinary should be reported. Please choose -git as
>     the version in the bugtracker if you do it that way, otherwise email
>     pacman-dev.
>     
>     Happy testing!
>     
>     -Dan
> 
> 



([Source](http://mailman.archlinux.org/pipermail/arch-dev-public/2011-August/021294.html)) Also the changelog can be found [here.](http://mailman.archlinux.org/pipermail/pacman-dev/2011-August/014039.html)

As you can see this is a RC version, so I expect  a stable version should hit the main repositories soon. I'm happy to see that one of my favorite distros is not sitting still on its laurels and improving itself.


