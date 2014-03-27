---
layout: post
title:  "Easy Bash function that copies a hostnames IP Address to your clipboard."
date:   2014-03-27 10:29:39
categories: bash
---

#Copy example.com IP to clickboard - Bash

The best thing about computers is that they do things for you. As a web developer at a company with over 200 clients, there are just some things that I do about 200 times a day. One of them is opening up iTerm2, and running *ping* or *nslookup* to retreive the IP of a given hostname. Here is what I don't like about doing that:

###Ping Takes way too long
This is proabably the first way everyone learns to get the IP of a host, but it is probably the slowest. The time to resolve the hostname, send the ICMP, wait for it to return, print to the screen and then manually exit the command is just too much.

###If I want NSLookup, I'll use NSLookup
Nslookup is a great utility and I use it when I need  a little bit more information. But when All i need is the IP of a hostname, there is just too much to look at, even when you know what you are looking for.

##The Solution
Below is a simple bash function that you can add to your .bash_profile in Mac OSX, I haven't tested this in ANY distributions of Linux, yet.

{% highlight bash %}
function tip(){
    host -t a $1 | awk '{print $4}' | egrep ^[1-9] | pbcopy
}
{% endhighlight %}

That is all their is to it.

Grab the [Gist][theGist] and feel free to fork it or fork this post.

[theGist]:    https://gist.github.com/connormckelvey/9791993
