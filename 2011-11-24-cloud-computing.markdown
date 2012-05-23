---
date: '2011-11-24 07:39:37'
layout: post
slug: cloud-computing
status: publish
title: Cloud Computing
wordpress_id: '1119'
categories:
- Tech
tags:
- ChromeOS
- CLI
- cloud
- cloud computing
- facebook
- google
- javascript
- JSON
- node.js
- programming
- spotify
- Tech
- twitter
- XML
---

Today’s computing needs increasingly demand for the use of cloud services, in this post the writers of Asinine Tech will be giving their widely different opinions on the use/abuse of cloud services for developers, enterprise and consumers.




### Fox: Power-User, Developer and CLI Fanboy


I have an interesting viewpoint, I'm both an end user and a developer, I’ve decided to not talk too much about development all too much because I pretty much only use C, PHP and Perl and avoid having anything to do with the user interface. I’m going to represent the “power user” for this large block of text.

After seeing [OS.js](//anderse.wordpress.com/os-js/”), I saw what cloud computing could really be. Not the bad experience you get from a slow port of chrome for Linux called ChromeOS. You feel like you are running on a real computer, not a browser. Its made me wonder why Google set their target so low, They created a worthless toy that works for maybe an elementary school or an internet café, but doesn’t work for much else. They want to make Google on top for everything? They should have really just designed a new desktop interface that kind of uses Chrome’s technologies to get the job done. I’ve never had a problem with some of the technologies used by browsers such as CSS and XML, they speed up development and make it easier to make a consistent interface; but they shouldn’t be used as the only part of the software. Javascript is not a solution to not having a programming language, HTML isn’t a great markup language for desktop UIs, and CSS just has too many issues with portability. What so many people seem to forget is that the web was never designed to handle our everyday lives, it was designed to share papers and information easily. Google has just bastardised the whole thing by going ahead and naming stuff in confusing ways, People think that native can exist in a browser now, Companies think that an office suite, email, and other applications that really need real time performance can live online with varying levels of success.

Some applications have lived on as desktop applications, while some people are moving to web music services some still use iTunes, no matter how clunky the interface may be, it still feels better. Even I would prefer iTunes compared to many other online services. Another example of software that people prefer to be native is game clients, this includes the social elements like Steam. Steam wouldn’t work if it was in a browser, nor would XFire. (if anyone remembers that) All of these applications require some level of native software, even though they could really just be on the web with a service that listens for special protocols``. People like that interface they get because it doesn’t get in their way, it stays in a notification area till it needs to be used.


### Cafejunkie:


Let me start off by saying I don’t necessarily represent the views of your average end user. I mostly see things from a software development perspective as that is the world that I live in. The way I use computers isn’t how most people use them.

First, I want to point out some projects that get “cloud computing” right.

[Spotify](http://www.spotify.com) is a good example. It is a native application but pulls it data from web (cloud) services while, because it is a native application, having the ability to play my music from my local storage. Social media is another area where one paradigm succeeds while the other fails. On one hand you have the “in the browser” paradigm which merges email, chat, status updates, etc into one clunky web interface. On the other hand, you have the native application+transparend web service paradigm. The “People Hub” in Windows Phone 7 is a near perfect way to handle social media.

Another flaw to the “everything in the browser” paradigm is bandwidth constraints.. With mobile plans now lacking unlimited data I don’t want to load an entire UI and fancy animations into my browser on a limited plan. I would rather have the UI elements be local and just pull the data I need, which is usually in text or a very small binary format. That paradigm is much more efficient.

All of the above reasons I think are proof that using only a browser is not the way to go and I would even argue in favor of killing the browser for all but documents, seeing as that was what HTML was originally designed for. To top it all off, I still don’t like the idea of browser technologies. The DOM sucks and Javascript is still slow inside of the browser. I much prefer native applications. Javascript, as a language (in my humble opinion) sucks for server-side programming. Also, HTML 5 and CSS3 for UI design and development are still pretty bad. Why move to those technologies for UI design when we have so many established technologies that just work (and work rather well)? I don’t want to suffer browser compatibility problems while programming a UI. Not only are compatibility problems rampant, HTML was never meant to design user interfaces whereas something like XAML was. Native applications that pull data from web services eliminate that suffering. I can use the UI technologies I’m used to while still taking advantage of web services without the mess that is the browser. Besides document viewing, the browser is old technology and was never designed to be used the way it is now. HTML is just a document markup language, not a language to design user interfaces with.

Even with cloud computing in it’s infancy, already the two paradigms are battling for control. Both want to use what’s known as a “thin client” but both paradigms define “thin client” differently. In my opinion Google gets it wrong while Microsoft (and others) gets it right. Here is why.

A “thin client” still needs to have native apps. What Google did is the wrong way to approach it. Don’t make people feel like they are locked in a browser. Make the fact that they are using web services transparent. Let them have a native application shell that pulls XML, JSON, or YAML data from web services transparently. No browser.

In the end I think Google’s “platform” will lose. People don’t want a browser, or worse, to be locked inside of one. Microsoft and Apple’s idea of “cloud” computing (native applications pulling in data from web services) will win out.


### staticsafe:


As a user of multiple operating systems (Windows, OSX, Linux), cloud computing can be quite the savior sometimes. I use Dropbox quite often to back up configuration files and to move file across systems easily. I’m also currently using Dropbox to manage my programming assignments that I get from school. I also use Github (cloud service?) to put my code up in the cloud to share with other people.

_Addressing vendor lock in_

Cloud computing addresses vendor lock in an interesting way from the layman’s perspective. It essentially forces developers to use standard file formats for files. This makes it easier for a user to move files **off** the cloud and aforementioned files still being easily accessible within the operating system of their choice, such as: a Google Docs document can be easily outputted to various formats which can be easily edited and shared offline.


### Raccoon: User Experience/ UI Design Pundit: At Large.


And when Eric Schmidt first announced ChromeOS, he basically said that it was the modern day implementation of the “thin client” idea. But per that idea, it means that the host computer would basically be useless..or “dumb” when not connected to the host. Which is a big problem for basically the whole world. Internet connections are not very speedy nor reliable in most of the world. And the half-assed attempts Google has made currently to rectify this situation is laughable at best. Gmail Offline is a rip of the tablet UI, Google Docs offline can only view things, and Calender can’t even add events. Also none of the “browser based” IDE’s support HTML offline, Cloud 9 being excluded, but that only “supports” HTML/JS/CSS and maybe one or two scripting languages. Basically, no one wants a dumb terminal because....... it’s kinda dumb.

Basically, I just want Web OS and stateless computing to come together. I can care less about the technology used for it, nor do I care about how it is done. I just want pretty, and I want things to work. Is that so hard of me to ask in 2011? As each day goes on, Google’s mentality of design being put behind raw engineering power is really starting to show. Only when something works a hell of a lot better than a competitors product, and not just by a bit. That is when I switch, and that gap is widening.

To add insult to injury, Google is going ahead and making their own “web-like” scripting language called Dart. As far as we know (though the information Google gave out), it is like Javascript but uses classes instead of prototypes per Javascript. And it runs multi threaded in the browser. From my “Oh look at this new shiny thing” perspective. It looks like yet-another-programing-language. Too little and too late on this one Google.

But I am honestly not against the idea of Cloud Computing, I find that idea to be up there. And I have the most ground to state my opinion on this as I have had a Cr-48 for almost a year. I really want ChromeOS to succeed in some form, just not the current form. Call me a fanboy, but I use basically Google everything, and because of that I want this product to work. I really do, but the flaws are so large that I just can’t. Not in the current form.

Let me add one more thing about the pains of ChromeOS. I’m going to walk you through the fun steps of handling a picture. First you plug in your camera, or get it from an email, or someone how get it onto your device. Second, you then go ahead and sign into Picasa. Second point Five, if you want to edit it, you upload to picnik or some other service. And said service is in flash, and due to them using pepper flash in ChromeOS because of sandboxing, it is slow. Third, you redownload the finished copy and then reupload to where ever you wanted it to be. (Facebook, Twitter, 4Chan, Etc.) And the same 3 to 4 step process applies to everything in this OS.

To summarize my little rant, “Ground” Computing is nice sometimes Google, and it rains when you stay in the cloud for too long..


### Acronyms:





	
  * HTML - HyperText Markup Language: the language of the web

	
  * XML - Extensible Markup Language: a markup language often used for communication between applications

	
  * JSON - JavaScript Object Notation: another markup language used for communication between applications

	
  * IDE - Integrated Development Environment: A tool that programmers can use to write software

	
  * JS - Javascript: A programming language used primarily on the web to create active content.

	
  * CSS - Cascading Style Sheets: A markup language designed to make styling websites easier.

	
  * XAML - Extensible Application Markup Language: An XML based markup language designed for creating applications and user interfaces.

	
  * YAML - YAML Ain't Markup Language(recursive acronym): A language designed for data interchange.

	
  * DOM - Document Object Model:

	
  * Node.js - Node.js is an event-driven I/O server-side JavaScript environment based on V8.


