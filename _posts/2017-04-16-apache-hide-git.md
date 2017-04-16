---
layout: post
title: "Hiding git Directories and Related Files in Apache"
date: 2017-04-16 21:55:13 +0800
categories: notes
tags: apache2
---

Let's start with something light in this first post. I using git for version control in one of my web applications, but the files in .git and .gitignore were accessible. I went searching of a simple solution and came accross [this](http://stackoverflow.com/questions/6142437/make-git-directory-web-inaccessible#answer-17916515).

The solution is simple, just append the following line in the **ROOT** of your webserver
{% highlight apache %}
RedirectMatch 404 /\.git
{% endhighlight %}

Then reload apache and viola! All git related files in any subdirectories are now hidden from prying eyes.