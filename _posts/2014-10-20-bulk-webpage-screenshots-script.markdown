---
layout: post
title:  "Bulk screenshot generator made in bash"
date:   2014-10-20 10:29:39
categories: bash
---

If you have ever tried to take screenshots of a 100 page website. You need this. It is a simple comand line tool that accepts a text file with a list of URLs takes screenshots of every page. For freelance web devs and designers this could come in handy for you. 

I wrote this script for my current employer. As a part of our development process we like to archive what websites liked like before and after we make major modifications or re-design them.

We have it plublished as a [repo](https://github.com/findsomewinmore/screenshots) with more detailed instructions.

{% highlight bash %}
#!/bin/bash

PAGES=()
FILE=$1
DIR=$2

# Read the file in parameter and fill the array named "array"
GETPAGES() {
    i=0
    while read line # Read a line
    do
        PAGES[i]=$line # Put it into the array
        i=$(($i + 1))
    done < $1
}

GETPAGES $FILE

for ((i = 0; i < ${#PAGES[@]}; i++))
do
    webkit2png ${PAGES[$i]} --fullsize --dir=$DIR
done

echo 'Screenshots Complete!'
{% endhighlight %}
