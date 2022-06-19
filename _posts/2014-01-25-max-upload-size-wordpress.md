---
id: 18
title: 'Increasing max upload size for self-hosted WordPress site'
date: '2014-01-25T10:35:25-07:00'
author: fosterizo
layout: post
guid: 'http://willfoster.doesntexist.org/blog/?p=18'
permalink: /2014/01/25/max-upload-size-wordpress/
categories:
    - Code
---

When you compose posts in WordPress and you click the "Add Media" button you are presented with a dialog to drag and drop or browse your file system for a file you want to add. You are presented with this lovely text "Maximum upload file size: 2MB." WTF man, awesome.gif is 5.1MB, and I don't want to shrink it to size (loss of awesomeness obvs.)
With help from <a href="http://wordpress.org/support/topic/increase-2mb-limit-when-uploading-a-photo-to-a-page" target="_blank">this post</a> I found out that WordPress uses the minimum of <code>post_max_size</code> and <code>upload_max_filesize</code> in php.ini to figure out this max size. Since I'm hosting my own blog now I couldn't care less what the size is as long as my server can handle it relatively easily. I don't want to be bound by these restrictions!
Long story short, I changed <code>upload_max_filesize</code> and <code>post_max_size</code> to be 8MB each. This allows a full resolution upload of awesome.gif.
<a href="https://fosteri.zone/wp-content/uploads/2014/01/Screen-Shot-2014-01-25-at-10.32.01-AM.png"><img class="aligncenter size-full wp-image-20" src="https://fosteri.zone/wp-content/uploads/2014/01/Screen-Shot-2014-01-25-at-10.32.01-AM.png" alt="Screen Shot 2014-01-25 at 10.32.01 AM" width="355" height="300" /></a>
&nbsp;
PS. I had to "Restart All Services" on my <a href="http://www.wampserver.com/en/" target="_blank">WAMP</a> server, I suspect only apache would need to be restarted to reload php.ini. Maybe it would auto-reload after a while, IDK just restart it already.