---
layout: post
title:  "Bash function that helps you quickly create bash aliases"
date:   2014-04-01 11:07:39
categories: bash
---

Adding an alias to your .bashrc or .bash_pofile is a quick and easy way to save a developer hundreds of keystrokes throughout the day. I have a couple dozen set up on my system for things like: undoing a git push, obtaining my external and internal IP Address and sourcing my .bash_profile. 

I add new aliases pretty frequently and doing so started to become a bother– having to edit my .aliases file (I store all aliases in a separate file to keep my .bash_profile clean), and then sourcing my .bash_profile all just to save a little bit of time. 

##The Solution
I created a bash function that adds the alias to my .aliases file and then reloads .bash_profile all in one command. 

{% highlight bash %}
function newalias() {
	echo alias $1=\"$2\" >> ~/.aliases
	source ~/.bash_profile
}
{% endhighlight %}

I store this function in my .functions file next to my .aliases file to keep things clean. After adding it to your .functions file or .bash_profile reload it by typing the following into your terminal emulator. 

{% highlight bash %}
source ~/.bash_profile
{% endhighlight bash %}

You can then add an alias by running the following command

{% highlight bash %}
newalias sayfoo 'echo foo'
{% endhighlight bash %}

The alias will becomes available immediately because the function newalias automatically reloads .bash_profile. Every once and a while you may want to go in and categorize related aliases and add some comments, jsut to keep things clean.

###A note for linux users
You should probably exchange any reference to .bash_profile for .bashrc or it will not work.

Grab the [Gist][theGist] and feel free to fork it or fork this post.

[theGist]:    https://gist.github.com/connormckelvey/9275367
