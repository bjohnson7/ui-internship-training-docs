---
description: "The Console description."
icon: "command-line"
layout: "setup"
title: "The Console"
weight: 11
accentIndex: 3
---

###### In this section, you will learn a bit about how to make sense of the Terminal messages.

<article id="readingTheCommandLine">

## Reading the Command Line

![Liferay Portal Startup](/images/LRP-startup-01.jpg)

1. Notice that the run command is executed at the `PATH/liferay-bundle/tomcat-version/bin` folder. It will not work anywhere else.
2. When you see this line, you know that Liferay is reading your `portal-ext.properties` file.
3. As Liferay is reading your `portal-ext.properties`, the system will also usually show what database it is using. You can use these lines to double check that Liferay is hooking onto the right database.
4. Every build will have this line. It tells you what edition, what version, and the date that it was built. When testing, you should make sure that this says the correct information.

![Liferay Portal Startup 2](/images/LRP-startup-02.jpg)

5. The deploy folder is created recreated at startup. The second line tells you that the scanner for the deploy folder has started. This means that Liferay will automatically scan the deploy folder for files to implement. You will notice that when you drop a file into this folder, within a few seconds Liferay will automatically scan the folder for files and deploy them.
6. This is the message notifying you that your application server has finished starting up and Liferay is up and running. Access your Liferay instance by using a browser to go to <http://localhost:8080>.

![Liferay Portal Shutdown](/images/LRP-shutdown.jpg)

7. This is what an exception looks like. It begins with the `ERROR` warning and is indented. If you get exceptions, it means something went wrong.

8. To shutdown the servers, type `CTRL + C`. You will see messages about things that are pausing and stopping and then at the very end it will ask you if you want to terminate the job. Enter `Y`. Normally, you want no exceptions at startup and shut down (this is something you should look for).

</article>