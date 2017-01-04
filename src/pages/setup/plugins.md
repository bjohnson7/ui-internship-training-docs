---
description: "Plugins description."
icon: "clip"
layout: "setup"
title: "Plugins"
weight: 12
accentIndex: 4
---

###### In this section, you will learn how to build a Liferay plugin and deploy it into Liferay portal.

<article id="whatArePlugins">

## What Are Plugins?

To make a plugin, you have to take the source code and compile it into a _.war_ file that you deploy into Liferay portal. Basically, you take the WAR file and drop it into the deploy folder (ie. `PATH/liferay-bundle/deploy`). Liferay will autoscan the deploy folder and process the `WAR` file for use within the portal.

</article>

<article id="settingBuildProperties">

## Setting _build.properties_

1. Use Git and set up the [plugins repository](//github.com/liferay/liferay-plugins), if you have not already done so.  See [See Section 7 (Getting Liferay's Source Code)](/setup/getting-liferays-source-code.html) for more information.

2. Create a `build.COMPUTER_NAME.properties` file in the `PATH/liferay-plugins` folder.

3. Edit the `build.COMPUTER_NAME.properties` file with a text editor. This `build.COMPUTER_NAME.properties` file should have similar lines as below, where `PATH` will be the path to your repository file:

	- The first property points to where your bundle is located.
		- When plugins are getting built, ant will pull in files from the bundle so you have to make sure that your plugin source version is the same as the portal source version.  If not, you may get usability errors when trying to build or deploy the plugins.
	- The second property points to where your deploy directory is.

	```properties
	{literal}app.server.dir=PATH/liferay-bundle/tomcat-8.0.32
	auto.deploy.dir=PATH/liferay-bundle/deploy{/literal}
	```

</article>

<article id="buildingPlugins">

## Building Plugins

Now that you have all the source code you need to make any Liferay plugin, we will start looking at the common uses for these files. There are only two ant commands that you will probably ever use in order to build a plugin.

1. To build a plugin, browse to `PATH/liferay-plugins` folder in your Terminal/Git Bash and run the following command on the plugin you want to build (ie. `PATH/liferay-plugins/portlets/random-bible-verse-portlet`):

	- This command will create a `.war` file of the plugin in your `PATH/liferay-bundle/dist` folder. To deploy the plugin, you can drag and drop the file into your deploy folder.

	```bash
	$ ant clean war
	```

2. To build a plugin _and_ have it automatically move to the deploy folder, browse to `PATH/liferay-plugins` folder in your Terminal/Git Bash and run the following command on the plugin:

	- This command will create a `.war` file and automatically move it to the location specified by your `auto.deploy.dir` property in the `build.COMPUTER_NAME.properties` file. The `ant clean war` command is contained within the `ant clean deploy` command.

	```bash
	$ ant clean deploy
	```

	- Notice that both commands contain the word `clean`. The `clean` task will delete any previously built `.war` file of that specific plugin before dropping in the new version.

These commands should be executed in the Terminal/Git Bash window at the directory of the plugin(s) that you want to use. For example, if you executed `ant clean war` in the `PATH/liferay-plugins/themes/welcome-theme` directory, you would find the `.war` file for the "Welcome Theme" in the dist folder. If you executed `ant clean war` in the `PATH/liferay-plugins/themes` directory, you would find the `.war` file for **ALL** themes in `PATH/bundle/dist` folder.

</article>