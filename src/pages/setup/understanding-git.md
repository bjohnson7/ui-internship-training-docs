---
description: "Understanding Git description."
icon: "fork"
layout: "setup"
title: "Understanding Git"
weight: 5
---

###### In this section, you will understand how Git works (repositories, remotes, and branches).

<article id="article-1">

## Overview

A version control system is a repository of files; often the files for the source code of computer programs, with monitored access. Every change made to the source code is tracked, along with who made the change, a comment regarding why the change was made, and references to problems fixed or enhancements introduced by the change.

Git is a version control system that is used to manage a project or a set of files as they change over time.

</article>

<article id="article-2">

## What is a repository?

A Git repository contains, among other things, the following:

* A set of **commit objects**
* A set of references to commit objects, called **branches** or **heads**

The Git repository is stored in the same directory as the project itself, in a subdirectory called **.git**

* There is only **ONE**//.git// directory, in the root directory of the project. The repository is stored in files alongside the project. There is no central server repository.

### What is a Commit Object?

A commit object contains three things:

* A set of **files**, reflecting the state of a project at a given point in time
* References to **parent commit objects**
* A **SHA1 name**, a 40-character string that uniquely identifies the commit object. The name is composed of a hash of relevant aspects of the commit, so identical commits will always have the same name.

### What is a Branch?

A **branch **or **head** is simply a reference to a commit object. Each branch has a name. By default, there is a branch in every repository called **master**. A repository can contain any number of branches. At any given time, the current commit that is selected is known as the "//current branch//." This branch is aliased to **HEAD** (Always in capitals). Creating branches in Git allow you to make changes in parallel rather than in series, allowing you to merge your changes in at a later time.

Liferay takes advantage of Git's branch structure to store multiple versions of Liferay Portal (6.0.x, 6.1.x, 6.2.x, 7.0.x, etc.).

![illustration of git branches](/images/git-branching.png)

</article>

<article id="article-3">

## Git's Workflow Model

##### With Git, you have to understand  3 repos:

1. **local** (your source code on your computer)
	- The copy of the source code stored locally on your computer. This is where you will be making your changes and updates to the source code before sending them to others to review. When you have made a commit (or set of changes to the source code) that you want to submit for review, you will push it from your **local** to your **origin** (See example picture below).
	- You also want to make sure to keep your local repository up to date with *upstream/master* (We will explain how to do this later).

2. **origin** (your source code on GitHub.com)
	- The copy of the source code stored in your GitHub account/cloud. It should be identical to **local/master**. Any commits you have submitted will be pushed from your **local machine** into your **origin (GitHub.com)** account.

3. **upstream** (the source code on GitHub.com where the main repository resides)
	- The copy of the source code where all final changes and updates are stored in Liferay's GitHub account/cloud. All the source code for Liferay Portal. Think of this as the Liferay cloud that contains only the reviewed and committed changes. Only a few people are allowed to push files into **upstream** (Brian Chan, Nate Cavanaugh, etc.). Even though you will be working with source code, you will never actually be pushing to this repository. Although your changes (or commits) might eventually make it here, they first will go through reviewers who then will push those commits to this repository.

![illustration of different repos](http://in.liferay.com/documents/114255/c81dda85-cd7e-41b5-bd49-a9a9de154923)

[//]: # (Perhaps add a subtitle here to make more clear? -Ben)

##### Then the git workflow looks something like this:

1. Brian **pushes** all content to the **upstream/master** branch to GitHub.com.
	* Repository:
		- Portal - <https://github.com/liferay/liferay-portal>
		- Plugins - <https://github.com/liferay/liferay-plugins>

2. We then **pull** these changes from **upstream/master** into our **local/master** branch to make sure everything is updated with the latest changes.

3. The changes from **upstream/master** get **merged** into our **local/master** branch for us to work with the latest source code.

4. We can create a new branch and begin working on any new changes to be submitted.

5. We then **push** our changes to our **origin** branch in our personal GitHub.com to be reviewed by others.

	* Repository:
		- Portal - <https://github.com/[**username**]/liferay-portal>
		- Plugins - <https://github.com/[**username**]/liferay-plugins>

If you noticed, your **local/master** and **origin/master** should **always** be identical to the **upstream/master** (Local Master = Origin Master = Upstream Master). **NEVER** make **ANY** changes to **ANY** of these **Master branches**.

For more information regarding Git's Workflow, you can visit their guide at <https://guides.github.com/introduction/flow>.

</article>