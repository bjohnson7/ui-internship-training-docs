---
description: "Building From Source description."
icon: "hammer"
layout: "setup"
title: "Building From Source"
weight: 10
---

###### In this section, you will utilize everything you have learned about Liferay in order to build from the source code into a Tomcat application server using Hypersonic as the database.

<article id="gettingTomcat">

## Getting Tomcat

In order to proceed, we need to first get Tomcat for Liferay to use.

1. Launch a Terminal/Git Bash window to your "_PATH/liferay-portal_" folder and run the following command:
	```
	$ ant -f build-dist.xml unzip-tomcat
	```
	- This command tells ant to look in the _build-dist.xml_ file and execute the _unzip-tomcat_ command. Ant will then delete preexisting Tomcat bundle if the folder name and version match, download the current version of Tomcat to the folder specified in your _app.server.**COMPUTER\_NAME**.properties_ file, and unzip the application server into the same directory.

2. If this Ant task is successful, you will see output similar to:
	<pre><code>
	$ ant -f build-dist.xml unzip-tomcat
	<br>
	Buildfile: PATH/liferay-portal/build-dist.xml
	<br>
	...
	<br>
	BUILD SUCCESSFUL
	<br>
	Total time: 10 seconds
	</code></pre>

</article>

<article id="buildingFromSource">

## Building from Source Code

Before you actually build your bundle from your portal repository, first double check to make sure that the file path listed in your _app.server.**COMPUTER\_NAME**.properties_ is set to the correct folder/directory. As long as it is set correctly, follow these steps:

1. Open a Terminal/Git Bash and **pull** the latest from the **upstream/master** branch. (Hint: you did this back when you were configuring Git).

2. Using the Terminal/Git Bash, browse to _PATH/liferay-portal_ and run the following command to build your source code:
	```
	$ ant setup-sdk
	```

3. If this Ant task is successful, you will see output similar to:
	<pre><code>
	$ ant setup-sdk
	<br>
	Buildfile: PATH/liferay-portal/build.xml
	<br>
	...
	<br>
	BUILD SUCCESSFUL
	<br>
	Total time: 2 minutes 30 seconds
	</code></pre>

4. Using the Terminal/Git Bash, browse to _PATH/liferay-portal_ and run the following command to build your source code:
	```
	$ ant all
	```

5. If this Ant task is successful, you will see output similar to:
	<pre><code>
	$ ant all
	<br>
	Buildfile: PATH/liferay-portal/build.xml
	<br>
	...
	<br>
	BUILD SUCCESSFUL
	<br>
	Total time: 10 minutes 22 seconds
	</code></pre>

6. Browse to **PATH/liferay-bundle/tomcat-8.0.32/bin** in the Terminal/Git Bash

7. Start up Tomcat by running the following command in the Terminal/Git Bash:
	- **Mac/Linux**
	```
	./catalina.sh run
	```
	- **Windows**
	```
	catalina.bat run
	```
	- \* We use **catalina** instead of double clicking on the **startup** files so that we can conveniently see the console and any errors that it may display/throw. If you run the startup file, the console will not stay open and you will have to look for the logs if there are any errors.

8. Open a web browser to **<http://localhost:8080>** and login using:
	- Login: **test@liferay.com**
	- Password: **test**

9. To stop the server, go to the Terminal/Git Bash and hit **CTRL + C**. If it asks you something, just type **Y**.

</article>

<article id="extraNotes">

## A Few Things to Note

In the future, **after** this initial set up, your subsequent order of operations might be something like this:

1. Update Git to latest **upstream/master**.
2. Edit the _**portal-ext.properties**_ file.
3. Run _ant all_ from _PATH/liferay-portal_.
4. Start Tomcat.

</article>