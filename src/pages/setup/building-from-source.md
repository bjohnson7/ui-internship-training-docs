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

1. Launch a Terminal/Git Bash window to your "//PATH/liferay-portal//" folder and run the following command:
	```
	$ ant -f build-dist.xml unzip-tomcat
	```
	- This command tells ant to look in the //build-dist.xml// file and execute the //unzip-tomcat// command. Ant will then delete preexisting Tomcat bundle if the folder name and version match, download the current version of Tomcat to the folder specified in your //app.server.**COMPUTER_NAME**.properties// file, and unzip the application server into the same directory.

2. If this Ant task is successful, you will see output similar to:

	```
	$ ant -f build-dist.xml unzip-tomcat
	Buildfile: PATH/liferay-portal/build-dist.xml
	...
	BUILD SUCCESSFUL
	Total time: 10 seconds
	```


</article>
{literal}



=== Building from Source Code ===

Before you actually build your bundle from your portal repository, first double check to make sure that the file path listed in your //app.server.**COMPUTER_NAME**.properties// is set to the correct folder/directory. As long as it is set correctly, follow these steps:

1. Open a Terminal/Git Bash and **pull** the latest from the **upstream/master** branch. (Hint: you did this back when you were configuring Git).

2. Using the Terminal/Git Bash, browse to //PATH/liferay-portal// and run the following command to build your source code:

{{{
$ ant setup-sdk
}}}

3. If this Ant task is successful, you will see output similar to:

{{{
$ ant setup-sdk
Buildfile: PATH/liferay-portal/build.xml
...
BUILD SUCCESSFUL
Total time: 2 minutes 30 seconds
}}}

4. Using the Terminal/Git Bash, browse to //PATH/liferay-portal// and run the following command to build your source code:

{{{
$ ant all
}}}

5. If this Ant task is successful, you will see output similar to:

{{{
$ ant all
Buildfile: PATH/liferay-portal/build.xml
...
BUILD SUCCESSFUL
Total time: 10 minutes 22 seconds
}}}

4) Browse to **PATH/liferay-bundle/tomcat-8.0.32/bin** in the Terminal/Git Bash

5) Start up Tomcat by running the following command in the Terminal/Git Bash:

**Mac/Linux**\\

{{{
./catalina.sh run
}}}

**Windows**\\

{{{
catalina.bat run
}}}
* We use **catalina** instead of double clicking on the **startup** files so that we can conveniently see the console and any errors that it may display/throw. If you run the startup file, the console will not stay open and you will have to look for the logs if there are any errors.

6) Open a web browser to **[[http://localhost:8080]]** and login using:

* Login: **test@liferay.com**
* Password: **test**

7) To stop the server, go to the Terminal/Git Bash and hit **CTRL + c**. If it asks you something, just type **Y**.

=== A Few Things to Note ===

In the future, **after** this initial set up, your subsequent order of operations might be something like this:

# Update Git to latest **upstream/master**.
# Edit the //**portal-ext.properties**// file.
# Run //ant all// from //PATH/liferay-portal//.
# Start Tomcat.

[[The Console|Continue to Section 11 (The Console)]]


{/literal}