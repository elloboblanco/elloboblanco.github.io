---
id: 689
title: 'Treefort Musician Map'
date: '2013-06-12T21:00:46-06:00'
author: fosterizo
layout: post
guid: 'http://www.williamgfoster.com/blog/?p=689'
permalink: /2013/06/12/treefort-musician-map/
categories:
    - Code
---

For those of you who know me, I enjoy a lot of things with computers, new technology, libraries, and fun projects. My initial idea for a heat map came to me while on a MTB ride and I thought it would be really cool to map the activity levels of different <a title="Strava" href="http://www.strava.com" target="_blank">Strava</a> athletes around the country to see who is more active (or logs on to <a title="Strava" href="http://www.strava.com" target="_blank">Strava</a> more regularly). I researched the API given to developers and it limited me to only people I follow, so I took a different route. I decided to map the concentration of musicians playing at a local music festival called <a title="Treefort" href="http://treefortmusicfest.com/" target="_blank">Treefort</a>. The data acquisition of this was way more manual than I expected, I pretty much just downloaded the HTML content of the Artists page and did some searching / regex replacements to find a list of musicians and the city they were based in. I made a set of the different cities they lived in and (unfortunately) looked up the Latitude and Longitude on Google. YES YES YES I realize I could have done this with a script, but in all it only took about an hour and I probably could have written a sufficient script in around the same amount of time. One thing to note is that two bands listed their city as "Earth" ... so cosmic man [stoner voice], they are now located at Lat 0, Long 0 in the Gulf of Guinea. Nonetheless I did it manually, then I wrote the file treefort-markers.js with an Excel spreadsheet and the concat() function. Lastly wrote us the HTML, CSS, and JS (thanks to underscorejs, Google fonts api, and the Google maps api) to wire it together in the main file <a title="treefort" href="https://fosteri.zone/treefort/treefort-2013">treefort.html</a>. I opted out of linking all the bands in favor of time and proof of concept (you could always Google their names too). Anyways, check it out and let me know what you think about it in the comments! (ps. make sure you click the markers to get a list of musicians near that map node!)
This project was completed a few months ago but I finally got around to writing this summary. Hope you enjoy it!
Findings: high concentration in the NW, and spread out more globally than I thought :)
<img class="size-full wp-image-691 aligncenter" src="https://fosteri.zone/wp-content/uploads/2013/06/Screen-Shot-2013-06-13-at-9.45.05-AM.png" alt="Screen Shot 2013-06-13 at 9.45.05 AM" width="964" height="545" />