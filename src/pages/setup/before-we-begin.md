---
description: "Before We Begin description."
icon: "menu-content"
layout: "setup"
title: "Before We Begin"
weight: 2
---

###### In this section, you will install programs that you will need, as well as set up the environment on your computer in order to use Liferay.

<article id="downloads">

## Things We Need to Download

- IM Client
	- [Adium](//adium.im/) (Mac)
	- [Pidgin](//pidgin.im/) (Windows)
- [SmartGit](//www.syntevo.com/smartgit/index.html)
- Text Editor
	- [Sublime Text](//www.sublimetext.com/)
	- [Atom](//atom.io/)
	- [EditPlus](//www.editplus.com/)
		- Use EditPlus for `.txt`, `.properties`, `.sql`, `.html` files
		- After installing, you will need to change some settings. Go to _Tools &rarr; Preferences &rarr; Files_. Uncheck the option to create a backup file  when saving. Also, go to _Files &rarr; Settings & Syntax_ and check the option to trim trailing spaces on save.
		- The `editplus.txt` file contains the reg key.
- Web browsers
	- [Chrome](//www.google.com/chrome)
	- [Firefox](//www.mozilla.org/en-US/firefox/new/)
		- [Firebug Plugin](//getfirebug.com/)
	- [Internet Explorer](//support.microsoft.com/en-us/help/17621/internet-explorer-downloads)
- [Java JDK](//www.oracle.com/technetwork/java/javase/downloads/index.html)
	1. Portal Master: [Java JDK 8](//www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html#jdk-8u101-oth-JPR)
	2. Portal 6.2.x: [Java JDK 7](//www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html#jdk-7u79-oth-JPR)
	3. Portal 6.1.x: [Java JDK 6](//www.oracle.com/technetwork/java/javasebusiness/downloads/java-archive-downloads-javase6-419409.html#jdk-6u45-oth-JPR)

#### Things We Need on Windows

[//]: # (EDITS -- need to add in the 'Instructions on Setting up Apache Ant' since it will be on this site rather than in.liferay.com. For now it links to the home page  -Ben)

- [7zip](//sourceforge.net/projects/sevenzip/)
	- Use 7zip for `.zip`, `.war`, and `.jar` files
	- 7zip is much faster than winzip.
- [Apache Ant](//ant.apache.org/)
	- [Instructions on setting up Apache Ant](/)

</article>

<article id="settingUpJDK">

## Setting Up Java JDK

Liferay is written in Java. Hence, you need Java.

#### Mac

1. Go to the [JDK downloads page](//www.oracle.com/technetwork/java/javase/downloads/index.html) in your browser.
2. Download the JDK installer for your desired Java version.
3. Double-click the downloaded installer.  (The installer is in `.dmg` format).
4. Follow the prompts to install the JDK. You will be asked to enter your administrator password before installation can proceed.
5. Java runtime is installed on your machine.  You can delete the `.dmg` file if desired.

#### Windows

1. Go to the [JDK downloads page](//www.oracle.com/technetwork/java/javase/downloads/index.html) in your browser.
2. Download the JDK installer for your desired Java version.
3. Install the JDK installer.
4. Go to your JDK directory and copy the path from the address bar:

	![Windows tutorial image](/images/setup-JDK-01.jpg)

5. Go to _Control Panel &rarr; System &rarr; Advanced &rarr; Environment Variables_. We will set your `JAVA_HOME` variable by clicking '**New...**'.

	![Windows tutorial image](/images/setup-JDK-02.jpg)

6. Add a new variable and fill out the fields as shown **EXCEPT** use your JDK path that you copied in step 4.

	![Windows tutorial image](/images/setup-JDK-03.jpg)

7. Verify that your `JAVA_HOME` variable is correct.

	![Windows tutorial image](/images/setup-JDK-04.jpg)

8. Add `JAVA_HOME` to the `PATH` variable. In the Environment Variables window, under the System variables section, look for your path variable and click '**Edit**'. The path variable should already exist and have values in it. **DO NOT DELETE THESE.** At the very beginning of the list of values, enter:

	```
	%JAVA_HOME%\bin;
	```

9. Check that your `PATH` variable is correct by opening a new command line and typing the word `path`. It should list the directory of your Java JDK. Make sure it is pointing to the right place and that there is only one JDK listed.

	![Windows tutorial image](/images/setup-JDK-05.jpg)

10. Lastly we need to double check your Java installation. In the command line, type `java -version` and a message regarding your Java version should be displayed:

	![Windows tutorial image](/images/setup-JDK-06.jpg)

</article>

<article id="changeFolderOptions">

## Change Folder Options

#### Mac

1. Launch the _Terminal_

2. Enter the command below to activate the ability to see the hidden files

	```
	$ defaults write com.apple.Finder AppleShowAllFiles TRUE
	```

3. Relaunch the Finder to make the changes take effect by killing it

	```
	$ killall Finder
	```

#### Windows

1. Go to _Control Panel &rarr; Folder Options &rarr; View_

2. Set your computer to show hidden files, folder, and drives.

3. Show extensions for known file types.

	![Folder options image](/images/change-folder-options.jpg)

</article>

<article id="setAntOpts">

## Set ANT_OPTS

`ANT_OPTS` is an environment variable that provides a list of arguments that you want to pass to the JVM that will run Ant.

#### Mac

1. Create a `.bash\_profile` _**if one does not already exist**_ at `~/.bash_profile`

2. Enter the contents below into the `.bash_profile`

	```
	export ANT_OPTS="-Xms2048m -Xmx4096m"
	```

3. Relaunch the Terminal by entering

	```
	$ source ~/.bash_profile
	```

#### Windows

1. Go to _Control Panel &rarr; System &rarr; Advanced &rarr; Environment Variables_

2. Add a new user variable named `ANT_OPTS`

3. Set it with only the value: `-Xms2048m -Xmx4096m`

	![Set ANT_OPTS tutorial image](//in.liferay.com/documents/114255/0d3cf0c8-4d12-4b3d-b7d1-09481d535773)

</article>

<article id="changeComputerName">

## Change Your Computer Name

**Remember your computer's name as you will be using it later in Liferay's configuration.**

#### Mac

1. Launch '**System Preferences**'

2. Click the '**Sharing**' icon

3. Type in what you want your new computer name to be

4. Close '**System Preferences**'

#### Windows

1. Right click on '**Computer**' on your desktop and choose **Properties**

2. On the Computer Name tab, click the '**Change Settings**' link

3. Click on '**Change...**' to rename the computer.

	![Change Computer Name Image](//in.liferay.com/documents/114255/034054a8-9587-4098-8a56-f6028659a582)

4. Type in what you want your new computer name to be

5. Click '**OK**'

6. Restart your computer for the changes to take effect.

</article>
