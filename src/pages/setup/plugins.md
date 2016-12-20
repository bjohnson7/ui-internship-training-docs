---
description: "Plugins description."
icon: "clip"
layout: "setup"
title: "Plugins"
weight: 12
---

###### In this section, you will learn how to build a Liferay plugin and deploy it into Liferay portal.

<article id="whatArePlugins">

## What Are Plugins?

To make a plugin, you have to take the source code and compile it into a _.war_ file that you deploy into Liferay portal. Basically, you take the WAR file and drop it into the deploy folder (ie. _**PATH**/liferay-bundle/deploy_). Liferay will autoscan the deploy folder and process the WAR file for use within the portal.

</article>

<article id="settingBuildProperties">

## Setting build.properties

1. Use Git and set up the [plugins repository](https://github.com/liferay/liferay-plugins), if you have not already done so.  See [See Section 7 (Getting Liferay's Source Code)](/setup/getting-liferays-source-code.html) for more information.

2. Create a _build.**COMPUTER\_NAME**.properties_ file in the "_**PATH**/liferay-plugins_" folder.

3. Edit the _build.**COMPUTER\_NAME**.properties_ file with a text editor.  This _build.**COMPUTER\_NAME**.properties_ file should have similar lines as below, where **PATH** will be the path to your repository file:

	- The first property points to where your bundle is located.
		+ When plugins are getting built, ant will pull in files from the bundle so you have to make sure that your plugin source version is the same as the portal source version.  If not, you may get usability errors when trying to build or deploy the plugins.
	- The second property points to where your deploy directory is.

	```
	app.server.dir=PATH/liferay-bundle/tomcat-8.0.32
	auto.deploy.dir=PATH/liferay-bundle/deploy
	```

</article>

<article id="buildingPlugins">

## Building Plugins

Now that you have all the source code you need to make any Liferay plugin, we will start looking at the common uses for these files. There are only two ant commands that you will probably ever use in order to build a plugin.

1. To build a plugin, browse to "_**PATH**/liferay-plugins_" folder in your Terminal/Git Bash and run the following command on the plugin you want to build (ie. "_**PATH**/liferay-plugins/portlets/random-bible-verse-portlet_"):

	- This command will create a _.war_ file of the plugin in your "_**PATH**/liferay-bundle/dist_" folder. To deploy the plugin, you can drag and drop the file into your deploy folder.

	```
	$ ant clean war
	```

2. To build a plugin _and_ have it automatically move to the deploy folder, browse to "_**PATH**/liferay-plugins_" folder in your Terminal/Git Bash and run the following command on the plugin:

	- This command will create a _.war_ file and automatically move it to the location specified by your **auto.deploy.dir** property in the _build.**COMPUTER\_NAME**.properties_ file. The `ant clean war` command is contained within the `ant clean deploy` command.

	```
	$ ant clean deploy
	```

	- Notice that both commands contain the word _clean_. The _clean_ task will delete any previously built _.war_ file of that specific plugin before dropping in the new version.

These commands should be executed in the Terminal/Git Bash window at the directory of the plugin(s) that you want to use. For example, if you executed _ant clean war_ in the "_**PATH**/liferay-plugins/themes/welcome-theme_" directory, you would find the _.war_ file for the "Welcome Theme" in the dist folder. If you executed _ant clean war_ in the "_**PATH**/liferay-plugins/themes_" directory, you would find the _.war_ file for **ALL** themes in "_**PATH**/bundle/dist_" folder.

</article>