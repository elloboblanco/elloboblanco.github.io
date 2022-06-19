---
id: 965
title: 'Treefort Musician Map v2.0'
date: '2014-03-07T01:14:00-07:00'
author: fosterizo
layout: post
guid: 'http://willfoster.doesntexist.org/blog/?p=965'
permalink: /2014/03/07/treefort-musician-map-v2-0/
categories:
    - Code
    - Music
---

First things first, go <a style="font-size: 16px; line-height: 1.5;" href="https://fosteri.zone/treefort/heatmap">HERE</a> to see what this post is about. If you are interested in how I did this ... keep reading.
Note: Nobody from <a href="http://treefortmusicfest.com">Treefort Music Fest</a> knows I did this, I just did it for fun.
Last year I made a heatmap to show the geographical layout of all the artists that would be playing at <a href="http://treefortmusicfest.com">Treefort Music Festival</a>. You can see that post <a title="Treefort Musician Map" href="https://fosteri.zone/blog/2013/06/12/treefort-musician-map/">here</a> and the original heatmap <a href="https://fosteri.zone/treefort/treefort-2013">here</a>. For v2.0 I had a couple of ideas that I wanted to implement.
<ul>
    <li>Search</li>
    <li>Thumbnail pictures of bands</li>
    <li>Better layout</li>
    <li>Auto scrolling to bands location on the map</li>
</ul>
<!--more-->
I started this task pretty much the same way I did last year. I went to <a href="http://treefortmusicfest.com/artists/">treefortmusicfest.com/artists/</a> and right-click "View Page Source" (⌘ + ⌥ + u). This let me download the raw HTML of that page which I just pasted into <a href="http://www.sublimetext.com/">Sublime Text</a>. I immediately noticed that the repetitive nature of the <code>&lt;article class="portfolio-post-entry"&gt;</code> nodes. This allowed me to match with regular expressions all 348 artist entries that I could find. Then through a couple macros and some more creative search and replace I generated <a href="https://fosteri.zone/treefort/artists-2014.js">artists-2014.js</a> which contained artist names, city and state, links to the artist page and the artist thumbnail, and the date they were playing at Treefort.
The only problem now (which I came across last year too) was that I could only scrape the city and state or city and country for the artists on the main artists page. Last year I solved this problem by figuring out all the unique location combinations and googling the latitude and longitude and manually copy and pasting these values, HUGE WASTE OF TIME. This year I decided to make use of the <a href="https://developers.google.com/maps/documentation/javascript/geocoding">Google Maps Geocoding API</a> which lets you submit basic location information (i.e., Boise, Idaho) and asynchronously sends you back a JSON response containing the latitude and longitude information according to The Google. One issue I came across was that the maps API limited me to 1 request per second, so I couldn't use this API on every page render (not to mention that would kill my page load). I tried through timeouts not to go faster than every second but you can see from the screenshots that I failed.
To solve this problem I wrote the code on my local box and made http requests via chrome dev tools, then I wrote back (through the js objects) the lat and lng information. I had to run this process a few times since I went over the quota multiple times.
<pre style="font-size: 12px;">var idx = 0;
geocoder = new google.maps.Geocoder();
_.each(artists, function(artist){
  if (!artist.lat)
  {
    setTimeout(function(){
      geocoder.geocode( { 'address': artist.city}, function(results, status){
        if (status == google.maps.GeocoderStatus.OK)
        {
          console.log("Artist: " + artist.name + " was great success");
          artist.geometry = {};
          artist.geometry.location = results[0].geometry.location;
          artist.geometry.location_type = results[0].geometry.location_type;
        }
        else
        {
          console.log("Artist: " +
            artist.name + " geocode was not successful for the following reason: " + status);
        }
      });
    }, 1050 * idx++); // attempt at staying under my 1 request per second quota
  }
});</pre>
<a href="https://fosteri.zone/wp-content/uploads/2014/03/Screen-Shot-2014-03-06-at-10.53.18-AM.png"><img class="aligncenter size-full wp-image-967" src="https://fosteri.zone/wp-content/uploads/2014/03/Screen-Shot-2014-03-06-at-10.53.18-AM.png" alt="Screen Shot 2014-03-06 at 10.53.18 AM" width="906" height="589" /></a>
Once all the artists had lat and lng information, I was able to <code>JSON.stringify()</code> the objects in memory and format them in <a href="http://www.sublimetext.com/">Sublime Text</a>. Now <a href="https://fosteri.zone/treefort/artists-2014.js">artists-2014.js</a> was complete with lat and lng information and ready for prime time.
The js code was pretty straight forward, I ditched all the combining same locations and grouping on a chart <a href="https://developers.google.com/maps/documentation/javascript/reference#Marker">marker</a> with a crappy looking <a href="https://developers.google.com/maps/documentation/javascript/reference#InfoWindow">InfoWindow</a> and went in favor of a list of artists (searchable) on the right hand side of the page. The list controls the map and makes <a href="https://developers.google.com/maps/documentation/javascript/reference#Marker">markers</a> and <a href="https://developers.google.com/maps/documentation/javascript/reference#InfoWindow">InfoWindows</a> as hovers are detected on the list. The underlying <a href="https://developers.google.com/maps/documentation/javascript/layers#JSHeatMaps">heatmap</a> is the exact same chart layer I was using before.
Truthfully the CSS was the hardest part for me, and there are still a few hacks and probably lots of errors but hey, it looks pretty good for now!
I did get some freebies this year from the <a href="http://treefortmusicfest.com/artists/">treefortmusicfest.com/artists/</a> parsing:
<ul>
    <li>Band thumbnails (incorporated into the <a href="https://developers.google.com/maps/documentation/javascript/reference#InfoWindow">InfoWindow</a>)</li>
    <li>Date of band playing (incorporated into the <a href="https://developers.google.com/maps/documentation/javascript/reference#InfoWindow">InfoWindow</a>)</li>
    <li>Artist page links (click on list items or anywhere in the <a href="https://developers.google.com/maps/documentation/javascript/reference#InfoWindow">InfoWindow</a> that pops up for each artist)</li>
</ul>
Bonus tasks:
<ul>
    <li><a href="http://httpd.apache.org/docs/current/mod/mod_rewrite.html">mod_rewrite</a> learning on my <a href="http://www.wampserver.com/en/">wamp</a> server, wanted to rewrite <a href="https://fosteri.zone/treefort/heatmap">https://fosteri.zone/treefort/heatmap</a> to <a href="https://fosteri.zone/treefort/heatmap.html">https://fosteri.zone/treefort/heatmap.html</a> so I didn't look like such a n00b</li>
</ul>
Check out my code and give me honest feedback! Make sure you check out <a href="https://fosteri.zone/treefort/treefort-2013">v1.0</a> as well to see the progression from 2013 to 2014