---
layout: post
title:  "Javascript bookmarklet that presents a native prompt with the hostname"
date:   2014-03-27 10:29:39
categories: bash
---

I use Chrome pretty much exclusively. There are very few things that I do not like about and I am usually very weary about overloading it with plugins to get it to do things that I want. The one thing that I despise, is the fact that they hide the http:// and trailing slash for hostnames. What is even worse is that they do not have an option to force it to show like Firefox does. 

At work I rely heavily on the domain/hostnames of our 200+. I frequently FTP into their server to make minor changes, or add thier FTP credentials into basecamp for another developer. For this reason, I find it so frusterating that Chrome does not provide an option similar to Firefox that would allow users to force the http:// and trailing slash to show.

##Why make it show?
I want to to show so that I can actually spcify the text that I want to highlight and copy for use in an FTP client, iTerm2 or Basecamp. Before I wrote bookmarklet below this was my process:

 1.  Click in address bar
 2.  Command + a (to select at)
 3.  Command + c (to copy)
 4.  Command + t (for a new tab)
 5.  Command + v (to paste) 
 6.  Manually select the text I needed to copy the hostname
 7.  Command + c
 8.  Command + w (To close the new tab, if I even remembered)
 9.  Use the text on my clipboard as soon as possible before I overwrite it with something.

I know that this process only takes about a second or two, but when I list out all the steps, it is kind of ridulous to have to do something like this 50+ times a day. 

##The Solution
{% highlight javascript %}
	javascript:void(
	  function(){var u = window.location.hostname.replace(/^www\./,'');
	  window.prompt('Copy URL to Clipboard CMD/CTRL + C',u);
	  }()
	);
{% endhighlight %}

My process has now been reduced to:

 1.  Click on bookmarklet
 2.  Command + C
 3.  Enter (To close the prompt)
 4.  Go on with my day

##The Bookmarklet

<a style="cursor: move; text-decoration: none; text-shadow: 0px 2px 2px rgba(0, 0, 0, .5); display: block; width: 200px; height: 50px; border-radius: 5px; background-color: #3B5998; text-align: center; line-height: 50px; font-size: 20px; font-family: Verdana, sans; color: #FFF; " href="javascript:void(function(){var u = window.location.hostname.replace(/^www\./,''); window.prompt('Copy URL to Clipboard CMD/CTRL + C',u); }());" onclick="alert('Drag me to the bookmarks bar'); return false;">Copy Hostname</a>

Grab the [Gist][theGist] and feel free to fork it or fork this post.

[theGist]:    https://gist.github.com/connormckelvey/9671914
