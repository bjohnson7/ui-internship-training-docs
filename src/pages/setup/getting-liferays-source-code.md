---
description: "Getting Liferay's Source code description."
icon: "download"
layout: "setup"
title: "Getting Liferay's Source code"
weight: 7
---

###### In this section, you will learn how to get the Liferay Source Code from your GitHub.com account.

<article id="forkingARepository">

## Forking a Repository

A _fork_ is a copy of a repository. Forking a repository allows you to freely experiment with changes without affecting the original project.

Most commonly, forks are used to either propose changes to someone else's project or to use someone else's project as a starting point for your own idea.

</article>

<article id="proposeChanges">

## Propose Changes to Liferay

A great example of using forks to propose changes is for bug fixes. To submit fixes for a bug you have found, you can:

1. Fork the repository.
2. Make the fix.
3. Submit a _pull request_ to the project owner.

</article>

<article id="forkLiferay">

## Fork Liferay Portal's Repository

Forking a repository is a simple two-step process. In order to begin making changes, you will need to fork the repository.

1. On GitHub.com, navigate to the [liferay/liferay-portal](https://github.com/liferay/liferay-portal)  repository.
2. In the top-right corner of the page, click **Fork**.

That is it! Now, you have a fork of the original _liferay/liferay-portal_ repository.

</article>

<article id="keepingForkSynced">

## Keep Your Fork Synced

As you submit bug fixes and updates to the upstream, or original, repository, it is good practice to regularly sync your fork with the upstream repository. To do this, you will need to use Git on the command line.

#### Step 1: Set Up Git

If you have not yet, you should first [set up Git](/setup/setting-up-git.html). Do not forget to [set up authentication to GitHub from Git](/setup/setting-up-git.html#authenticatingWithGithub) as well.

#### Step 2: Create a Local Clone of Your Fork

Right now, you have a fork of the _liferay/liferay-portal_ repository, but you do not have the files in that repository on your computer. Let us create a clone of your fork locally on your computer.

1. On GitHub.com, navigate to **your fork** of the _liferay-portal_ repository.
2. Under your repository name, click **Clone or download**.
3. In the Clone with HTTPs section, click the copy icon to copy the clone URL for the repository.
4. Open Terminal/Git Bash.
5. Type `git clone`, and then paste the URL you copied in Step 2. It will look like this, with your GitHub username instead of YOUR-USERNAME:

	```
	$ git clone https://github.com/YOUR-USERNAME/liferay-portal
	```

6. Press **Enter**. Your local clone will be created.

	<pre><code>
		$ git clone https://github.com/YOUR-USERNAME/liferay-portal
		<br>
		Cloning into 'liferay-portal' ...
		<br>
		remote: Counting objects: 10, done.
		<br>
		remote: Compressing objects: 100% (8/8), done.
		<br>
		remove: Total 10 (delta 1), reused 10 (delta 1)
		<br>
		Unpacking objects: 100% (10/10), done.
	</code></pre>

Now, you have a local copy of your fork of the _liferay-portal_ repository!

#### Step 3: Configure Git to Sync Your Fork with the Original _liferay-portal_ Repository

When you fork a project in order to propose changes to the original repository, you can configure Git to pull changes from the original, or upstream, repository into the local clone of your fork.

1. On GitHub.com, navigate to the [liferay/liferay-portal](https://github.com/liferay/liferay-portal) repository.
2. Under your repository name, click **Clone or download**.
3. In the **Clone with HTTPs section**, click the copy icon to copy the clone URL for the repository.
4. Open Terminal/Git Bash.
5. Change directories to the location of the fork you cloned in **Step 2: Create a local clone of your fork**.

	- To go to your home directory, type just `cd` with no other text.
	- To list the files and folders in your current directory, type `ls`.
	- To go into one of your listed directories, type `cd your_listed_directory`.
	- To go up one directory, type `cd ..`

6. Type `git remote -v` and press **Enter**. You will see the current configured remote repository for your fork.

	<pre><code>
		$ git remote -v
		<br>
		origin    https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
		<br>
		origin    https://github.com/YOUR_USERNAME/YOUR_FORK.git (push)
	</code></pre>

7. Type `git remote add upstream`, and then paste the URL you copied in Step 2 and press **Enter**. It will look like this:

	```
	$ git remote add upstream https://github.com/liferay/liferay-portal.git
	```

8. To verify the new upstream repository you have specified for your fork, type `git remote -v` again. You should see the URL for your fork as `origin`, and the URL for the original repository as `upstream`.

	<pre><code>
		$ git remote -v
		<br>
		origin    https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
		<br>
		origin    https://github.com/YOUR_USERNAME/YOUR_FORK.git(push)
		<br>
		upstream    https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git (fetch)
		<br>
		upstream    https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git (push)
	</code></pre>

Now, you can keep your fork synced with the upstream repository with a few Git commands. For more information, see [Syncing a Fork](/setup/setting-up-git.html).

</article>

<article id="nextSteps">

## Next Steps

The sky is the limit with the changes you can make to a fork, including:

- Creating branches: Branches allow you to build new features or test out ideas without putting your main project at risk.
- Opening pull requests: If you are hoping to contribute back to the original repository, you can send a request to the original author to pull your fork into their repository by submitting a pull request.

</article>