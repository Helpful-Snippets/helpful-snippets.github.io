---
layout: post
title:  "Bash function captures your working directory and opens it in the browser as a url"
date:   2014-04-04 11:07:39
categories: bash
---

Everyone organizes their projects in a different way. So this helpful snippet may not apply to everyone, but it contains some useful code that can help out just about anyone, no matter their project organization patters.

##Background
At work we host and maintain over 200 of our clients websites, so I am forced to cleanly organize the files that reside on my computer in order to stay sane. My directory structure looks something like this:

{% highlight bash %}
function newalias() {
	~/Dropbox/Sites/Current Employer/
}
{% endhighlight %}

Within my current employer directory I have 200+ directories using the client's domain name as the directory name and each has its own git repository. 

With so many clients I spend most of my day using iTerm2 to navigate, copy files, push to Github and Bitbucket, optimize images and all sorts of other great stuff. It is so much faster than pointing and clicking within Finder. This being said, I needed a way to pull up the client's site after editing, pushing and deploying.


##The Solution
The *open* command can be used to open a file or in this case a URL using the default application. The *pwd* command will print your entire current directory, so all I had to do was grab the last directory concatenate it on to "http://" to tell *open* the string was a URL and, whiz-bang- mission accomplished.

{% highlight bash %}
function o() {
	result=${PWD##*/}
	open 'http://'$result
}
{% endhighlight %}

To execute this command I navigate to the websites directory on my computer and type "o". You can really name it anything you want but this was the simplest and fastest name I could think of.

Upon typing "o" and hitting enter, Google Chrome opens the website in a new tab.


Grab the [Gist][theGist] and feel free to fork it or fork this post.

[theGist]:    https://gist.github.com/connormckelvey/9979612
