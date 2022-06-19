---
id: 1209
title: 'Treefort 2017 &#8211; Devfort Analytics'
date: '2017-03-27T11:56:25-06:00'
author: fosterizo
layout: post
guid: 'https://locohost.fosteri.zone/?p=1209'
permalink: '/?p=1209'
categories:
    - Code
    - Music
---

<h1 class="file_title post_title">Website</h1>
<div>
Website data backs up the claim that Treefort is a "Festival of Discovery"; over half our users have never visited our site before and over half of our engagement comes from the month of the festival.
<h3>LAST 30 DAYS</h3>
<ul>
 	<li><b>141,749 sessions</b></li>
 	<li><b>79,878 unique users</b></li>
 	<li><b>398,392 page views</b></li>
</ul>
On average people view 2.81 pages / session and spend about 3:08 minutes on the site. 50.13% of our users are first time users and our "bounce rate" is 47.47%.
<h3>FULL YEAR</h3>
<ul>
 	<li><b>289,426 sessions</b></li>
 	<li><b>163,757 unique users</b></li>
 	<li><b>735,178 page views</b></li>
</ul>
On average people view 2.5 pages / session and spend about 2:30 minutes on the site. 55.98% of our users are first time users and our "bounce rate" is 49.24%.
<h1>Mobile Apps</h1>
App statistics from April 1st 2016 - March 25th 2017. One interesting thing to note, over half of our installs come from the week before and week of Treefort, this has happened two years in a row now. Also, we had <b>2,339 shared schedules</b>!!! This gives us a good idea of where we can focus our efforts for #Treefort2018 ... <b>SOCIAL</b>.
<h3>PUSHWOOSH INFORMATION</h3>
<ul>
 	<li><b>8,209 devices total (registered w/ Pushwoosh)</b>
<ul>
 	<li>4,132 devices w/ push enabled (50.33%)</li>
 	<li>4,079 iOS users w/ push</li>
 	<li>53 Android users w/ push</li>
 	<li>12 Languages</li>
</ul>
</li>
</ul>
<h3>ITUNES CONNECT</h3>
<ul>
 	<li><b>~5,430 users on iOS</b>
<ul>
 	<li>iTunes Connect recorded 1,810 installations over the last year (opt-in only). On average 33% of our users "opt in" on iTunes, so ... 1810 * 3 = 5430</li>
</ul>
</li>
</ul>
<h3>GOOGLE PLAY</h3>
<ul>
 	<li><b>2,119 Installs on active devices over the last year</b>
<ul>
 	<li>Active Devices: The number of devices that have been active in the previous 30 days and on which the application is currently installed.</li>
</ul>
</li>
</ul>
<h1>Festival API</h1>
Our festival API backs both the website and mobile apps with the proper data needed to show attendees the right data. It answers questions like "What is the full list of events?" (i.e., GET /events) or "What are all the current line lengths?" (i.e., GET /lines), and so forth.
<h3>API HIGHLIGHTS</h3>
<ul>
 	<li><b>1.77 million total API requests for the entire month of March</b></li>
 	<li><b>1.35 million of them happening during the festival (~76%)</b></li>
 	<li>The busiest hour was Thursday 3/23 at 8pm MDT where we answered ~27k requests, or 450 requests / min, or 7.5 requests / second.</li>
</ul>
<h3>API STATISTICS BY DAY</h3>
<ul>
 	<li>Day Before Treefort
<ul>
 	<li><b>92.8k</b> total API Requests from 3/21 @ 3am - 3/22 @ 3am</li>
</ul>
</li>
 	<li>First "Festival Day"
<ul>
 	<li><b>246k</b> total API Requests from 3/22 @ 3am - 3/23 @ 3am</li>
</ul>
</li>
 	<li>Second "Festival Day"
<ul>
 	<li><b>317k</b> total API Requests from 3/23 @ 3am - 3/24 @ 3am</li>
</ul>
</li>
 	<li>Third "Festival Day"
<ul>
 	<li><b>328k</b> total API Requests from 3/24 @ 3am - 3/25 @ 3am</li>
</ul>
</li>
 	<li>Fourth "Festival Day"
<ul>
 	<li><b>298k</b> total API Requests from 3/25 @ 3am - 3/26 @ 3am</li>
</ul>
</li>
 	<li>Fifth "Festival Day"
<ul>
 	<li><b>164k</b> total API Requests from 3/26 @ 3am - 3/27 @ 3am</li>
</ul>
</li>
</ul>
<a href="http://ec2-18-144-75-252.us-west-1.compute.amazonaws.com/wp-content/uploads/2017/03/analytics-fort.png"><img class="alignnone wp-image-1212" src="http://ec2-18-144-75-252.us-west-1.compute.amazonaws.com/wp-content/uploads/2017/03/analytics-fort.png" alt="2017-analytics-fort" width="739" height="394" /></a>
<h1>Cost Analysis</h1>
<h3>AWS COSTS</h3>
<b>$1,025.09 for the last 12 months; current month (March) is projected to cost $805.75 putting the cost of a "Treefort Year" on AWS at ~2k. </b>We are certain we can drive this cost down next year by improving some of our products (CDN in front of S3, ETL outside of Data Pipeline, etc.)
<h3>WPENGINE COSTS</h3>
<b>~$500/year to run our WPEngine site.</b> $29/mo for 25k visits; we went over our 25k included visits in January 2017 (~13k visits over quota, $42 total) and March 2017 (~133k visits over quota, $162 total).
<h1>Volunteer Analysis</h1>
625 volunteer hours tracked!!! This means for each hour we spent dev-ing this year we aquired ~13 new app users and ~260 website users.
</div>
<div id="footer"></div>