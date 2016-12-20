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
[//]: # (I have not been able to get Digsby to work AT ALL...do we still include? -Ben)

* IM Client
	- [Adium](http://adium.im/) (Mac)
	- [Digsby](http://www.digsby.com) (Windows)
* [SmartGit](http://www.syntevo.com/smartgit/index.html)
* [Sublime Text](http://www.sublimetext.com/)
* Web browsers
	- [Chrome](http://www.google.com/chrome)
	- [Firefox](http://www.mozilla.org/en-US/firefox/new/)
		+ [Firebug Plugin](http://getfirebug.com/)
	- [IE](https://support.microsoft.com/en-us/help/17621/internet-explorer-downloads)
* [Java JDK](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
	1. Portal Master: [Java JDK 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html#jdk-8u101-oth-JPR)
	2. Portal 6.2.x: [Java JDK 7](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html#jdk-7u79-oth-JPR)
	3. Portal 6.1.x: [Java JDK 6](http://www.oracle.com/technetwork/java/javasebusiness/downloads/java-archive-downloads-javase6-419409.html#jdk-6u45-oth-JPR)

### Things We Need on Windows

[//]: # (EDITS -- need to add in the 'Instructions on Setting up Apache Ant' since it will be on this site rather than in.liferay.com. For now it links to the home page  -Ben)

* [7zip](http://sourceforge.net/projects/sevenzip/)
	- Use 7zip for .zip, .war, and .jar files
	- 7zip is much faster than winzip.
* [EditPlus](http://www.editplus.com/)
	- Use EditPlus for `.txt`, `.properties`, `.sql`, `.html` files
	- After installing, you will need to change some settings. Go to Tools -> Preferences -> Files. Uncheck the option to create a backup file  when saving. Also, go to Files -> Settings & syntax and check the option to trim trailing spaces on save.
	- The editplus.txt file contains the reg key.
* [Apache Ant](http://ant.apache.org/)
	- [Instructions on setting up Apache Ant](/)\

</article>

<article id="environmentSetup">

## Environment Setup

###### Use the screenshots and instructions to help you set up your environment.

### Setting up Java JDK

Liferay is written in Java. Hence, you need Java.

#### Mac

1. Go to the [JDK downloads page](http://www.oracle.com/technetwork/java/javase/downloads/index.html) in your browser.
2) Download the JDK installer for your desired Java version.
3) Double-click the downloaded installer.  (The installer is in *.dmg* format).
4) Follow the prompts to install the JDK. You will be asked to enter your administrator password before installation can proceed.
5) Java runtime is installed on your machine.  You can delete the *.dmg* file if desired.

#### Windows

1. Go to the [JDK downloads page](http://www.oracle.com/technetwork/java/javase/downloads/index.html) in your browser.
2. Download the JDK installer for your desired Java version.
3. Install the JDK installer.
4. Go to your JDK directory and copy the path from the address bar:

![Windows tutorial image](http://in.liferay.com/documents/114255/bf9b0693-faa4-4c61-a121-6059333056c5)

5. Go to Control Panel -> System -> Advanced -> Environment Variables. We will set your **JAVA_HOME** variable by clicking '**New...**'.

![Windows tutorial image](http://in.liferay.com/documents/114255/28fc4295-2cc1-4db2-b46c-63eda75c7968)

6. Add a new variable and fill out the fields as shown **EXCEPT** use your JDK path that you copied in step 4.

![Windows tutorial image](http://in.liferay.com/documents/114255/bc66cb5a-802e-4440-9749-06b9ea203f73)

7. Verify that your **JAVA_HOME** variable is correct.

![Windows tutorial image](http://in.liferay.com/documents/114255/45784a91-31a3-49bd-88b0-1af4ee2fa553)

8. Add **JAVA_HOME** to the **PATH** variable. In the Environment Variables window, under the System variables section, look for your path variable and click '**Edit**'. The path variable should already exist and have values in it. **DO NOT DELETE THESE.** At the very beginning of the list of values, enter:

```
%JAVA_HOME%\bin;
```

9. Check that your **PATH** variable is correct by opening a new command line and typing the word `path`. It should list the directory of your Java JDK. Make sure it is pointing to the right place and that there is only one JDK listed.

![Windows tutorial image](http://in.liferay.com/documents/114255/cad452fe-521b-4f5f-b378-1280651e4fa8)

10. Lastly we need to double check your Java installation. In the command line, type `java -version` and a message regarding your java version should be displayed:

![Windows tutorial image](http://in.liferay.com/documents/114255/e91e0381-0994-4fa1-b20d-34bc2620fca2)

### Change Folder Options

#### Mac
1. Launch the *Terminal*

2. Enter the command below to activate the ability to see the hidden files

```
$ defaults write com.apple.Finder AppleShowAllFiles TRUE
```

3. Relaunch the Finder to make the changes take effect by killing it

```
$ killall Finder
```

#### Windows
1. Go to Control Panel -> Folder Options -> View
2. Set your computer to show hidden files, folder, and drives.
3. Show extensions for known file types.

![Folder options image](http://in.liferay.com/documents/114255/38dde78b-5a20-4350-aa99-bad181021bab)

### Set ANT_OPTS

###### **ANT_OPTS** is an environment variable that provides a list of arguments that you want to pass to the JVM that will run Ant.

#### Mac

1. Create a **.bash_profile** _if one does not already exist_ at `~/.bash_profile`
2. Enter the contents below into the **.bash_profile**

```
export ANT_OPTS="-Xms2048m -Xmx4096m"
```

3. Relaunch the Terminal by entering

```
$ source ~/.bash_profile
```

#### Windows

1. Go to Control Panel -> System -> Advanced -> Environment Variables
2. Add a new user variable named **ANT_OPTS**
3. Set it with only the value: `-Xms2048m -Xmx4096m`

![Set ANT_OPTS tutorial image](http://in.liferay.com/documents/114255/0d3cf0c8-4d12-4b3d-b7d1-09481d535773)

### Change Your Computer Name

###### Remember your computer's name as you will be using it later in Liferay's configuration.

#### Mac

1. Launch '**System Preferences**'

2. Click the '**Sharing**' icon

3. Type in what you want your new computer name to be

4. Close '**System Preferences**'

#### Windows

1. Right click on '**Computer**' on your desktop and choose **Properties**

2. On the Computer Name tab, click the '**Change Settings**' link

3. Click on '**Change...**' to rename the computer.

![Change Computer Name Image](http://in.liferay.com/documents/114255/034054a8-9587-4098-8a56-f6028659a582)

4. Type in what you want your new computer name to be

5. Click '**OK**'

6. Restart your computer for the changes to take effect.

</article>
