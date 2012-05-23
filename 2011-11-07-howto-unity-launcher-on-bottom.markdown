---
date: '2011-11-07 04:20:25'
layout: post
slug: howto-unity-launcher-on-bottom
status: publish
title: 'Howto: Unity Launcher on Bottom'
wordpress_id: '1036'
author: FloatingGoat
categories:
- Howtos
- Linux
tags:
- linux
- ubuntu
- unity
---

Ubuntu 11.10 launched with a slightly revamped unity interface bringing subtle yet important changes. One of these changes being the relocation of the Ubuntu button onto the launcher. Some people saw this as unneeded, out of place, or just a bit silly. Most people didn't look past the little things enough to realize that this small change brought along the possibility that the launcher would some day be movable. Well, thanks to a Russian interface tweaker named "Paulo", that possibility is now a reality. Paulo has ingeniously figured out a way to move the unity launcher to the bottom of the screen. What I am going to do, is show you how to get this for yourself and what problems you may run into.



**How to get it**

NOTE: 32Bit Only! I do not accept any responsibility for any negative impact on your system that may occur from enabling this!




	
    1. Go ahead and download [unityshell.tar.lzma](http://dl.dropbox.com/u/47006748/unityshell.tar.lzma) and extract it to your home folder.

	
    2. Open up a terminal, and get your copy and paste ready, one line at a time now.





> mkdir -p ~/.compiz-1/plugins
cd ~/unityshell
cp libunityshell.so ~/.compiz-1/plugins/
mkdir /tmp/unityshell
cp *.png /tmp/unityshell/
cd /tmp/unityshell/
chmod 644 *.png
sudo chown root:root *.png
sudo cp *.png /usr/share/unity/4/





	
  1. Now just log out then log back in.




[![](http://asininetech.com/wp-content/uploads/2011/11/Screenshot-at-2011-11-07-00-48-51-1024x575.png)](http://asininetech.com/wp-content/uploads/2011/11/Screenshot-at-2011-11-07-00-48-51.png)




**Known Issues**

As you can see from the picture there are some issues. To start off, the first and most annoying bug that I have found; If you have more than instance of a certain application running and you pan out to view your open windows it doesn't always show every window that is actually open. Though the next few bugs are much more minor than the previous they should still be considered. If it is preferred to use the dash in a minimized view this tweak may not exactly be your cup of tea because when you do use minimized dash with this tweak the dash sort of detaches itself from the top panel and looks like it is broken(shown above) but using maximized dash of course is completely flawless. Unfortunately you aren't going to be able to drag the shortcuts from the dash or the desktop to the launcher when you are using this tweak. Thankfully you can still pin the items to the launcher using the unity quick list. Although most features like auto-hide surprisingly still work great given the launchers new placement the unity desktop still seems to think that the launcher is on the left with this tweak so there are still a few noticeable incompatibilities. For instance when you use workspace switcher there is a big black bar where the unity launcher used to be and you are also unable to drag and drop desktop shortcuts to the space where the panel used to be.

**Conclusion**

Now that you know what you are getting into, its your choice if you wanna take it for a spin or not. I say give it a shot I kinda like it even though it can get a bit tedious sometimes. I originally stumbled upon this tweak on [webupd8.org](http://www.webupd8.org/2011/10/how-to-move-unity-launcher-to-bottom-of.html). If you want more info or just want to see the original posts where this tweak first came about [forum.ubuntu.ru](http://forum.ubuntu.ru/index.php?topic=171694.0) and [ubuntu.onego.ru](http://ubuntu.onego.ru/articles/solves/launcher-unity-vnizu-ekrana/) both web pages are in Russian so Google translate is advised. If you would like to undo this just run:


> rm ~/.compiz-1/plugins/libunityshell.so



