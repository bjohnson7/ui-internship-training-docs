---
description: "Tips for Searching description."
icon: "magnifier"
layout: "toolkit"
title: "Tips For Searching"
weight: 8
---

###### Much of the leg-work of what you'll be doing will involve a significant amount of searching--whether that be for a class name or a property name. Being able to search well is an invaluable asset for your experience and effectiveness while working in UI. Below are some tips for searching well:

<article id="sublimeText">

## Using Sublime Text

[Search](http://sublime-text-unofficial-documentation.readthedocs.org/en/latest/search_and_replace/search_and_replace_files.html) using `CTRL + SHIFT + F`. This has been mentioned before, but seriously, you will find yourself using it a lot. If you know that you're looking for a certain type of file, you can search, for example, in `*.css` or `*.java`, `*.jsp`.

It may also be helpful for searching to learn Sublime's regular expressions. Sublime uses Boost syntax for regular expression. Check out [Boost](http://www.boost.org/doc/libs/1_47_0/libs/regex/doc/html/boost_regex/syntax/perl_syntax.html) documentation to learn how to use regular experessions in Sublime.

**Note:** To enable regular expression search in sublime, make sure the leftmost button (the one with the symbols `.*`) is selected next to the search box.

What do you do when you've found everything you're looking for? Place a bookmark. Smart bookmarking will save you from searching for the same things over and over again. You can set a bookmark at the current line by pressing `CTRL + F2`. Press `F2` to cycle through your current bookmarks.

</article>

<article id="DevTools">

## Google Developer Tools

Google's Developer Tools come standard with Chrome, and are incredibly neat and easy to use. While some prefer Firebug, Google Chrome is great for understanding the breakdown of different elements, and what styles or functions are being applied to them. You can easily tweak styles, remove classes, etc., quickly, and without any permanent changes being applied.

**Resource:** Check out [Code School's tutorials on Google's Developer Tools](http://discover-devtools.codeschool.com/) for learning the Chrome debugger.

</article>

[//]: # (Do I even include this section? Firefox seems to ship with Firebug built in...or at least the szearch function. Also, seems like Chrome's search function has improved greatly)

<article id="firebug">

## Firebug

Firefox's built in developer tools are next-to-useless compared to Chrome's Developer Tools, but Firebug (different than Firefox's developer tools) can be incredibly useful, especially when looking to see where specific elements are used. The search function will look through the entire HTML markup, and is more effective in this capacity than Chrome.

</article>

<article id="fileExplorer">

## Windows File Explorer

Windows File Explorer is great if you need to track down a file or a directory, but it can be incredibly misleading when trying to find keywords, especially ones that are parts of long strings of text. Use Sublime for searching for anything that isn't obvious.

</article>

<article id="methods">

## Methods

If you're stuck, ask for help, whether that be a coworker or Google. A lot of people have done exactly what you're currently doing. Don't be afraid of asking for help.

It was mentioned once, but Firebug is amazing with searching.

Choose good keywords. Searching the entire liferay-portal repository with a keyword that is too broad or common will return you hundreds of results. Use keywords that are likely to only appear in a few places.

</article>