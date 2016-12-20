---
description: "Understanding Source Code description."
icon: "code-file"
layout: "setup"
title: "Understanding Source Code"
weight: 4
---

###### In this section, you will learn the difference between the source code (source) and the compiled code (bundle).

<article id="sourceVsCompiled">

## Source Code vs. Compiled Code

*Uncompiled code* (Source code) is constantly being updated, depending on which branch/version it is. This is the code that you would check out from our repositories, edit, and update. Any changes to the source code are committed into their repositories and branches. The source code is uncompiled code – if you want to use it, you have to use ant commands to compile it. The source branches/versions are named like: 6.0.x, 6.1.x, 6.2.x, 7.0x, etc.

*Compiled code* is derived from the source code. Basically, someone had to take the source code and compile it for people to use.

A *Liferay bundle* contains the compiled code and an application server. The bundle is what customers download and use in production environments. The bundles are named after their source versions, like: 6.0.6, 6.0.12, 6.1.0, 6.1.10, 7.0.1, etc.

Essentially, you can consider the compiled code (bundle) as an “out of the box” ready to be used Liferay portal that anyone can use. Bundles are what we offer to our customers through our website.

You can download bundles at [[https://www.liferay.com/downloads|www.liferay.com/downloads]].

</article>

<article id="gettingSourceCode">

## How do you get Source Code?

Since Liferay is an open source software, all source code is available on GitHub for download and use. (See [github.com/liferay/liferay-portal](http://github.com/liferay/liferay-portal)).

For every CE version, including *master*, the source code is available for anyone to check out. However, EE source code is only available to Liferay developers. The compiled version of the EE source code is what customer's fix packs are generated from.

Unlike compiled code, source code can be used to customize the core functionalities of Liferay.

Take for example a cake. The source code would be the recipe for the cake. Modifying any source code would be like modifying the recipe.  The compiled code is the cake batter.  The bundle is the finished cake.

</article>

<article id="branchesVstrunk">

## Branches vs. Trunk

![Branches diagram](http://in.liferay.com/documents/114255/77c83c9c-bd26-432d-8747-8d63d6db85e6)

*Trunk* is the latest and greatest of the source code. There are many branches of Liferay, so you need to be sure which branch you are working on. (6.1.x, 6.2.x, 7.0.x, master, etc).

*Branches* are like the limbs of trunk – each branch includes some improvement over the previous branch(es), but once branched, there will not be any new improvements or functionality added. (New changes would remain in trunk until the next branch spawns). When a new branch is created, it will be similar to source code in trunk, until trunk has new improvements and updates added to it.

</article>

<article id="whySourceCode">

## Why do I need to get the Source Code?

If you find a bug in a bundle, it is good practice to find out if it is also in the latest source code of bundle version. If it exists in the latest source code of that bundle version, a fix should be applied to all versions of that bundle.

If the bug is on the latest bundle version, we should see if that issue also exists in previous bundle versions  as well.  If it does, the fix will need to be backported to all the previous versions.

In order to submit any fix, you would need to get the latest source code for your respective branch and submit a fix in the source code.  Once your fix gets merged into its respective branch, QA will build a bundle and test your fix.

</article>
