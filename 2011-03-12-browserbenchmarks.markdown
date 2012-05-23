---
date: '2011-03-12 00:29:24'
layout: post
slug: browserbenchmarks
status: publish
title: In Depth Browser Performance Benchmarking
wordpress_id: '476'
author: TingPing
categories:
- Blogging
- Linux
- News
- Software
- Tech
- Windows
tags:
- '2011'
- 2d
- acceleration
- acid
- acid3
- alpha
- android
- at
- bench
- benchmark
- benchmarking
- beta
- browser
- browsers
- build
- canary
- candidate
- chrome
- chromium
- css
- css3
- dev
- difference
- explorer
- fast
- ff
- ff4
- field
- firefox
- future
- futuremark
- gl
- hadware
- how
- html
- html5
- ie
- ie9
- internet
- is
- java
- javascript
- keeper
- linux
- mac
- mark
- mine
- minefield
- mobile
- net
- nightly
- opera
- osx
- overview
- peace
- peacekeeper
- performance
- rc
- release
- render
- rendering
- safari
- script
- software
- speed
- spider
- sun
- sunspider
- test
- testing
- tests
- update
- verses
- vista
- vs
- war
- web
- webgl
- windows
- xp
---

This year the browser wars are heating up as all of the big browsers are getting major updates and web standards like html5 and css3 are getting more widely supported so I decided to see how they are going with some in depth testing on all of the browsers. Things like UI and features are up for debate due to personal preference but nobody can refuse some solid benchmarking results.

Tools used:



	
  1. [Peacekeeper](http://futuremark.com/peacekeeper), a browser benchmarking tool created by futuremark, the best at benchmarking, which includes various tests for all around performance.

	
  2. [SunSpider](https://www.webkit.org/perf/sunspider/sunspider.html) which is a Javascript only benchmark

	
  3. [Acid3](http://www.acid3.org/) which tests for general standards support

	
  4. [CSSTest](http://www.howtocreate.co.uk/csstest.html) which calculates how long it takes to render CSS








### IE9:




Thought I'd start out with the biggest update of them all, and probably the biggest surprise to most, Internet Explorer 9. Most people tired of the recent mediocrity of previous releases will most likely skip past IE as it will be more of the same, but these results suggest otherwise.














PeaceKeeper


SunSpider


Acid3






[![IE9 Test results (6689 POINTS)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-09.57.22-150x150.png) ](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-09.57.22.png)


[![IE9 - sunspider (201ms)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-10.05.38-150x150.png) ](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-10.05.38.png)


[![IE9 Acid3 Results (95/100)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-10.08.58-150x150.png) ](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-10.08.58.png)













### FF4:




Firefox, the browser of choice for many power-users, is coming out with version 4 soon (Just hit release candidate) and it needs to keep a leg up on Internet Explorer and catch up to Chrome the new kid on the block, although no longer that new, but from these results I find them the least impressive and by far the slowest performer.














PeaceKeeper


SunSpider


Acid3






[![FF4 Peacekeeper results (5256)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-10.27.07-150x150.png)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-10.27.07.png)


[![FF4 SunSpider results (214ms)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-10.28.31-150x150.png)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-10.28.31.png)


[![FF4 Acid3 Test (97/100)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-10.29.55-150x150.png)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-10.29.55.png)













### Opera11:




Opera 11 just came out not long ago so i thought id throw it in here to see how it performs. Despite being  by far the least used of the browsers tested today the results seem show its one of the most impressive of the 4.














PeaceKeeper


SunSpider


Acid3






[![Opera Peacekeeper Results (10882)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-11.11.06-150x150.png)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-11.11.06.png)


[![Opera SunSpider Results (224ms)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-11.12.27-150x150.png)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-11.12.27.png)


[![Opera Acid3 Results (100/100)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-11.12.46-150x150.png)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-11.12.46.png)













### Chrome12:




Lastly but certainly not least Chrome, which just hit version 12 a few days ago, continues to be a fast performer with an equally fast release schedule. Every release the performance seems to increase to where it finally topped Opera in some tests.














PeaceKeeper


SunSpider


Acid3









### [![Chrome PeaceKeeper Results (11869)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-11.51.56-150x150.png)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-11.51.56.png)





[![Chrome SunSpider Result (235ms)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-11.50.38-150x150.png)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-11.50.38.png)


[![Chrome Acid3 Result (100/100)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-11.29.08-150x150.png)](http://asininetech.com/wp-content/uploads/2011/03/Screenshot-2011-03-11-at-11.29.08.png)













### Conclusion:




Comparing the performance between the browsers the conclusions I came to were: Firefox needs to work on performance to keep up with the others, Internet Explorer proved they can still perform, Opera continues to be underrated, and Chrome will be on version 100 by this time next year(Plus it's pretty fast). All modern browsers make a good choice as performance isn't everything, but me personally will be staying with Chrome. Here is a final comparison of the PeaceKeeper scores and I included Safari just for good measure. [Comparison](http://asininetech.com/?attachment_id=515)









*performance varies based on hardware and software.
