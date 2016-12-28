---
description: "Setting Up Git description."
icon: "github"
layout: "setup"
title: "Setting Up Git"
weight: 6
accentIndex: 5
---

###### In this section, you will learn how to setup your GitHub.com account to begin downloading your source code from the Liferay repositories.

<article id="createGithubAccount">

## Create a GitHub Account

1. Create an account on **[github.com](https://github.com)** using your **FIRSTNAME.LASTNAME@LIFERAY.COM** email as your email address.  Do not use the word **liferay** in your username.
2. Add your **Full Name** to your GitHub public profile.
3. Add a picture using gravatar (be sure to use your **FIRSTNAME.LASTNAME@LIFERAY.COM** email address).
4. Email **IT-support@liferay.com** with your **GITHUB USERNAME** if you need access to the private repositories.
5 Follow [[Brian Chan (brianchandotcom)](https://github.com/brianchandotcom) on GitHub.com. 

</article>

<article id="setupGit">

## Setting Up Git

1. Download and install the latest version of Git at <http://git-scm.com/downloads>.

	If you are on Windows, and plan to use Git on other terminals besides Git Bash, you'll want to select "**Run Git from the Windows Command Prompt**" when you get to the screen that says "_Adjusting your PATH environment_".

	Examples of programs/utilities that use Git include:

	- Alloy UI
	- Git based Sublime Text 2 plugins
	- IntelliJ
	- Eclipse
	- and many more...

	![installing git](/images/install-git.jpg)

	Git Bash and Command Prompt have essentially the same functionality except Git Bash is Linux based and was designed to be used with Git. It is up to you to use whichever terminal you prefer; some use the command prompt and some use Git Bash.

	If you are on Windows, it is recommended that you select "**Checkout as-is, commit Unix-style endings.**" Windows adds an extra character to the end of each line in text files, and Liferay will only accept files with Unix-style line endings. Sublime Text should be able to read files with Unix-style endings if you are on a Windows computer.

	![configure line endings](/images/change-line-endings.png)

2. Relaunch the Terminal by running the following command in your Terminal/Git Bash:

	```bash
	$ source ~/.bash_profile
	```

3. Add your full name to your `.gitconfig` file by running the following command in your Terminal/Git Bash: (Replace the `FULL NAME` placeholder token with your full name).

	```bash
	$ git config --global user.name "FULL NAME"
	```

4. Add your Liferay email address (**@liferay.com**) to your **.gitconfig** file by running the following command in your Terminal/Git Bash: (Replace the **FIRSTNAME.LASTNAME** placeholder token with your actual email).

	```bash
	$ git config --global user.email "FIRSTNAME.LASTNAME@liferay.com"
	```

5. If you are on Windows, you will need to add a setting to your **.gitconfig** file by running the following command in your Terminal/Git Bash:

	```bash
	$ git config --global core.longpaths true
	```

</article>

<article id="authenticatingWithGithub">

## Authenticating with GitHub

When you connect to a GitHub repository from Git, you will need to authenticate with GitHub using either HTTPS or SSH.

#### Connecting over HTTPS (recommended)

If you [clone with HTTPS](https://help.github.com/articles/which-remote-url-should-i-use/#cloning-with-https-urls-recommended), you can [cache your GitHub password in Git](https://help.github.com/articles/caching-your-github-password-in-git/) using a credential helper.

#### Connecting over SSH

If you [clone with SSH](https://help.github.com/articles/which-remote-url-should-i-use/#cloning-with-ssh-urls), you must [generate SSH keys](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/) on each computer you use to push or pull from GitHub.

</article>