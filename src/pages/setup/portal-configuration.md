---
description: "Portal Configuration description."
icon: "gear"
layout: "setup"
title: "Portal Configuration"
weight: 9
---

###### In this section, you will learn how to configure Liferay Portal's settings to prepare it to run from source code.

<article id="customPropertiesFiles">

## Custom *.Properties Files

In order to get Liferay Portal to compile and run correctly, we have to configure some paths. The `*.properties` files will determine the location of the bundle, what application server to use, and the version of the application server that will be used.

The `.COMPUTER_NAME.properties` files allow you to override any configuration settings found in the `*.properties` files.

Liferay Portal will read files in this order of precedence:

1. `COMPUTER_NAME.properties`
2. `default.properties` file, where the default properties file is what comes bundled in Liferay's source code. Therefore, whatever properties you set in your `COMPUTER_NAME.properties` file will supercede whatever is in the default file.

To find out what the default properties are and what alternative properties you can override, use a text editor to open the `default.properties` file and search for the line(s) that set the property. Then, copy and paste only the ones you want to override into your `COMPUTER_NAME.properties` file.

As a rule, **ONLY** edit the `*.COMPUTER_NAME.properties` files.

</article>

<article id="setBuildAndAppServerProperties">

## Setting _build.properties_/_app.server.properties_

1. Create a new file called `build.COMPUTER_NAME.properties` and `app.server.COMPUTER_NAME.properties` inside the `liferay-portal` folder created in [Section 7 (Getting Liferay's Source Code)](/setup/getting-liferays-source-code.html).

	- The `COMPUTER_NAME` can be found in [Section 2 (Before We Begin)](/setup/before-we-begin.html)

2. Edit your `build.COMPUTER_NAME.properties` with the following lines in a text editor:

	```properties
	javac.memoryMaximumSize=1024m
	```

3. In your `app.server.COMPUTER_NAME.properties` files, you should specify the location of your Liferay Portal source code and where you want your application server to be located. To do this, your `app.server.COMPUTER_NAME.properties` file should have similar lines as below, where `PATH` will be the path to your desired location:

	- The first property (`app.server.type`) defines what type of app server we are going to be running
	- The second property (`app.server.parent.dir`) determines which directory will contain the application server's files (i.e. the bundles folder). Make sure to put **YOUR** path.
	- The third property (`app.server.tomcat.dir`) sets where the Tomcat files are located.
	- _NOTE: If you have not created a bundle in this directory, do not worry, you will in the next section._

	```properties
	{literal}app.server.type=tomcat
	app.server.parent.dir=PATH/bundles
	app.server.tomcat.dir=PATH/bundles/tomcat-8.0.32{/literal}
	```

	- _NOTE: you can use relative paths in your file as well_

	```properties
	{literal}app.server.type=tomcat
	app.server.parent.dir=${project.dir}/bundles
	app.server.tomcat.dir=${app.server.parent.dir}/tomcat-8.0.32{/literal}
	```

	- _NOTE: you must use forward slashes "/" in these values_

</article>

<article id="settingPortalExtProperties">

## Setting _portal.properties_/_portal-ext.properties_

To override settings in the `portal.properties` file, you will need to create a file called `portal-ext.properties`. (You will be working with this file a lot).

1. Duplicate the `portal-developer.properties` file, found at `PATH/liferay-portal/portal-impl/src`

2. Rename the file: `portal-ext.properties`.

3. Open the `portal-ext.properties` file in a text editor and edit the file to look like:

	```properties
	{literal}theme.css.fast.load=false
	theme.css.fast.load.check.request.parameter=true
	theme.images.fast.load=false
	theme.images.fast.load.check.request.parameter=true

	javascript.fast.load=true
	javascript.log.enabled=false

	layout.template.cache.enabled=false

	browser.launcher.url=

	combo.check.timestamp=true

	freemarker.engine.cache.storage=soft:1
	freemarker.engine.resource.modification.check.interval=0

	minifier.enabled=false

	openoffice.cache.enabled=false

	velocity.engine.resource.modification.check.interval=0

	com.liferay.portal.servlet.filters.cache.CacheFilter=false
	com.liferay.portal.servlet.filters.etag.ETagFilter=false
	com.liferay.portal.servlet.filters.header.HeaderFilter=false
	com.liferay.portal.servlet.filters.themepreview.ThemePreviewFilter=true{/literal}
	```

	- _NOTE: When developing, you sometimes need to unminify your javascript code. To do this, set `javascript.fast.load=false`_

4. We will be moving this file to one folder above the tomcat directory (ie. `PATH/bundles`).

</article>

<article id="settingDevMode">

## Setting Liferay into Developer Mode

In order to develop in Liferay you need to set Liferay into developer mode so you will not have to start and stop the server every time you make a change.

1. Browse to `PATH/liferay-bundle/tomcat-7.0.27/bin`.

2. Using a text editor, open the `setenv.sh` file if you are on a Mac/Git Bash or the `setenv.bat` file if you are on Windows.  Add the following line at the end of the file:

	```bash
	 -Dexternal-properties=portal-ext.properties
	```

3. Your file should look something like:
	- **Mac/Git Bash - `setenv.sh`**

	```bash
	{literal}JAVA_OPTS="$JAVA_OPTS -Dfile.encoding=UTF8 -Dorg.apache.catalina.loader.WebappClassLoader.ENABLE_CLEAR_REFERENCES=false -Duser.timezone=GMT -Xmx1024m -XX:MaxPermSize=256m -Dexternal-properties=portal-ext.properties"{/literal}
	```

	- **Windows - `setenv.bat`**

	```bat
	{literal}if exist "%CATALINA_HOME%/jre${jdk.windows.version}/win" (
		if not "%JAVA_HOME%" == "" (
			set JAVA_HOME=
		)

		set "JRE_HOME=%CATALINA_HOME%/jre${jdk.windows.version}/win"
	)

	set "JAVA_OPTS=%JAVA_OPTS% -Dfile.encoding=UTF8 -Djava.net.preferIPv4Stack=true -Dorg.apache.catalina.loader.WebappClassLoader.ENABLE_CLEAR_REFERENCES=false -Duser.timezone=GMT -Xmx1024m -XX:MaxPermSize=256m -Dexternal-properties=portal-ext.properties"{/literal}
	```

</article>
