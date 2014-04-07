---
layout: post
title:  "Javascript bookmarklet that forces all text on a page to use Comic Sans"
date:   2014-04-07 10:29:39
categories: funny
---

As you probably know, Comic Sans is one of the best typefaces available. Pretty much every attribute of Comic Sans makes it an excellent choice for print, mobile and web. In the past few years, products like Typekit and Google Fonts have forced developers and designers to use open webfonts so that their designs are consistent across all browsers and platforms.

I don't know about you but this puts me into a blinding rage, especially because there are no fonts available through these services that offer anything close to Comic Sans. 



##The Solution
{% highlight javascript %}
	javascript:void(
	  function(){
	    var elems = document.getElementsByTagName("*");
		for (var i=0; 1 < elems.length; i++){
			elems[i].style.fontFamily = "Comic Sans, Comic Sans MS, cursive";
		}
	  }()
	);
{% endhighlight %}

This Javascript bookmarklet allows me to change the font of any webpage to Comic Sans. I use this to increase readability on sites like Wikipedia, Stack Overflow and the New York times. Of course this is only a Javascript solution, so only users of this bookmarklet benefit. 

Spread the work on Twitter and reclaim your browser.


##The Bookmarklet

<a style="cursor: move; text-decoration: none; text-shadow: 0px 2px 2px rgba(0, 0, 0, .5); display: block; width: 200px; height: 50px; border-radius: 5px; background-color: #3B5998; text-align: center; line-height: 50px; font-size: 20px; font-family: Verdana, sans; color: #FFF; " href="javascript:void(function(){var elems = document.getElementsByTagName('*');for (var i=0; 1 < elems.length; i++){elems[i].style.fontFamily = 'Comic Sans, Comic Sans MS, cursive'; } }());" onclick="alert('Drag me to the bookmarks bar'); return false;">Comic Sans Me</a>
