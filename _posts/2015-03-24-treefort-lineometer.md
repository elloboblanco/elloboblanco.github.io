---
id: 1005
title: 'Treefort 2015 Lineometer'
date: '2015-03-24T07:39:26-06:00'
author: fosterizo
layout: post
guid: 'http://willfoster.doesntexist.org/blog/?p=1005'
permalink: /2015/03/24/treefort-lineometer/
categories:
    - Code
    - Music
---

Well folks, I'm writing this year just before <a href="http://treefortmusicfest.com" target="_blank">Treefort Music Fest</a> '15 to announce the project that some of my righteous coworkers and I helped create…the <a title="Treefort Lineometer!" href="https://treefort-venue.herokuapp.com/#/" target="_blank">Treefort Lineometer!</a> Because I didn't have much to do with the technical side of the app this year, I'll just give an overview of the features, the major technologies we used, and award some kudos to all the hardworking developers that helped out with this project.
<h2>Team Members</h2>
All of these guys worked their asses off for this feature; I was mostly a pencil pusher and project manager. But I DID check in code…once. ;)
<ul>
 	<li style="padding-left: 30px;"><a href="https://twitter.com/philmerrell" target="_blank">Phil Merrell</a>: Original Treefort app creator and our special liaison to Treefort people.</li>
 	<li style="padding-left: 30px;"><a href="https://twitter.com/dcryan22" target="_blank">Daniel Ryan</a>: Badass developer who made the most excellent loading icon (with D3), general client side development, manager app, and visitor app.</li>
 	<li style="padding-left: 30px;"><a href="https://twitter.com/Birdy_0" target="_blank">Alberto Ruis</a>: Badass developer in charge of syncing Treefort schedules with our backend, general client side dev, manager app, and visitor app.</li>
 	<li style="padding-left: 30px;"><a href="https://twitter.com/waded" target="_blank">Wade Dorrell</a>: Main venue tracker designer and code ninja. Special thanks to this guy for making usability #1.</li>
 	<li style="padding-left: 30px;"><a href="https://twitter.com/DietzTweetz" target="_blank">Blake Dietz</a>: Back-end ninja, front-end ninja, authentication and security ninja, and all around badass developer.</li>
</ul>
<strong>NOTE:</strong> They all did much more than what I've mentioned next to their names; this is just a brief summary. Special thanks to Drew Lorona and Eric Gilbert at Treefort Music Fest for facilitating this app!
<h2>Motivation</h2>
After Treefort 2014, I met with <a href="https://twitter.com/philmerrell" target="_blank">Phil Merrell</a> and some other prospective developers for beers and to brainstorm about what technological improvements we could make for this year's festival. We came up with some great ideas and let them simmer until I got back in touch with Phil this January. We immediately got the ball rolling on what we thought would add the most value for the least amount of work (borrowing from the <a href="http://en.wikipedia.org/wiki/Pareto_principle" target="_blank">20/80 Pareto principle</a> commonly referenced in SCRUM). That project would eventually become <a href="https://treefort-venue.herokuapp.com/#/" target="_blank">The Treefort Lineometer</a>, and with Phil's help, it would be embedded as a tab in the <a href="https://www.sencha.com/products/touch/" target="_blank">Sencha</a> touch app he built for Treefort!
<h2>Features</h2>
<ul>
 	<li style="padding-left: 30px;">Real-time venue updates: When a manager changes the "currently playing" or line status, all the clients get updated in real-time. This is accomplished using <a href="https://www.firebase.com/" target="_blank">Firebase</a> and <a href="https://www.firebase.com/docs/web/libraries/angular/api.html" target="_blank">Angular Fire</a>.</li>
 	<li style="padding-left: 30px;">Security: Manager app authentication; only people with the code can update the venues. This is accomplished using <a href="https://nodejs.org/" target="_blank">NodeJS</a>.</li>
 	<li style="padding-left: 30px;">Last updated: When looking at the venue update, is the update even relevant? Intelligent text highlighting gives visual cues.</li>
 	<li style="padding-left: 30px;"><strong>Lineometer!</strong>: How long is the line?! Should visitors even bother making the trek from their current party?</li>
 	<li style="padding-left: 30px;">Free text + filtered lists of artists in the manager screen: Choose from the 20 artists who could be playing at this venue vs. a list of 300+. Impromptu show? Use the free text field and all the clients will get updated in the same way.</li>
 	<li style="padding-left: 30px;">Intelligent wrist band visuals: Depending on the day of the festival and the venue being managed, the manager app will show the valid list of wrist bands.</li>
</ul>
<h2>Major Technologies</h2>
<ul>
 	<li style="padding-left: 30px;"><a href="https://www.firebase.com/" target="_blank">Firebase</a> for our real-time venue tracking back-end</li>
 	<li style="padding-left: 30px;"><a href="https://angularjs.org/" target="_blank">AngularJS</a> and <a href="https://www.firebase.com/docs/web/libraries/angular/api.html" target="_blank">Angular Fire</a> for our front end web app</li>
 	<li style="padding-left: 30px;"><a href="https://www.heroku.com/" target="_blank">Heroku</a> for static file hosting</li>
 	<li style="padding-left: 30px;"><a href="https://nodejs.org/" target="_blank">NodeJS</a> for authentication logic</li>
 	<li style="padding-left: 30px;"><a href="https://github.com" target="_blank">Github</a> for collaboration, feature tracking, and workflow management</li>
</ul>
<h2>Integration</h2>
With help from Phil and the people at Treefort, we were lucky enough to get our Venue Tracker in the Treefort Music Fest <a href="https://itunes.apple.com/us/app/treefort-music-fest/id608181277">iOS</a> and <a href="https://play.google.com/store/apps/details?id=com.treefortmusicfest.treefort&amp;hl=en">Android</a> apps. The Sencha touch framework that Phil used made integration relatively easy; more or less we get a web view inside the app to do what we want with!
<h2>Obstacles</h2>
For our team, some notable obstacles were:
<ul>
 	<li style="padding-left: 30px;">Limited funding, and thus limited connections on our Firebase plan. Thanks to Treefort for coming up with some cash to help us!</li>
 	<li style="padding-left: 30px;">Limited time. Since we are all full time developers at WhiteCloud Analytics, our day jobs and families had to take priority. This is why everyone who worked on this project is such a badass, donating their time and skills for this.</li>
 	<li style="padding-left: 30px;">Limited understanding of users. This seems like it is always a problem with software projects, but we went through several iterations of a line visualization until we got one that we thought would make sense to the most people. After interviewing our significant others and coworkers, our current design (the one with badges) was the most easily understood.</li>
</ul>
<h2>Takeaway</h2>
Download the Treefort Music Fest app and use it at the festival! Get up-to-date information about which venues have the longest lines. If you are a venue manager, don't hesitate to contact me personally or any of the members of the team. We will be monitoring and providing updates throughout the festival on our <a href="https://twitter.com/treefortlines" target="_blank">Treefortlines</a> twitter account, so feel free to contact us there too!
<ul>
 	<li style="padding-left: 30px;">Main URL of the app: <a href="https://treefort-venue.herokuapp.com/#/" target="_blank">https://treefort-venue.herokuapp.com/#/
</a></li>
 	<li style="padding-left: 30px;">Manager app URL and password have been distributed to the people who will be using it. :)</li>
</ul>
<h2>Screens</h2>
<a href="https://fosteri.zone/wp-content/uploads/2015/03/screens-blurred.png"><img class="aligncenter size-full wp-image-1028" src="https://fosteri.zone/wp-content/uploads/2015/03/screens-blurred.png" alt="screens-blurred" width="1015" height="743" /></a>
<hr />
If you liked this, consider reading the <a title="Treefort 2015 Lineometer Retrospective" href="https://fosteri.zone/2015/04/02/treefort-lineometer-retrospective/">retrospective</a> as well