---
description: "Understanding Liferay Portal description."
icon: "liferay-logo-2-tiny"
layout: "setup"
title: "Understanding Liferay Portal"
weight: 8
---

###### In this section, you will learn about Liferay and how it runs.

<article id="whatIsLiferay">

## What is Liferay Portal?

Liferay Portal is a Java-based web platform with features commonly required for the development of websites and portals. Liferay includes a built-in web content management system allowing users to build websites and portals as an assembly of themes, pages, portlets/gadgets and a common navigation. Liferay is sometimes described as a content management framework or a web application framework.

Although Liferay offers a sophisticated programming interface for developers, no programming skills are required for basic website installation and administration.

Liferay is bundled with a servlet container such as Apache Tomcat.

#### What is Needed to Run Liferay?

Liferay needs **Java**, an **application server**, and a **database** to run. Our baseline setup is to use Apache Tomcat as the app server and Hypersonic/MySQL for the database.

#### What is an App Server?

An app server handles communications to the database on one hand and connections to the web application (Liferay) on the other.

App servers that Liferay supports:

- **Tomcat (Apache)**
- Geronimo (Apache)
- Glassfish (Oracle)
- JBoss (Red Hat)
- Jetty (Eclipse)
- JOnAS
- OracleAS
- SUN JSAS
- Resin (Caucho)
- Websphere (IBM)
- Weblogic (Oracle)

#### What is a Database?

A database organizes and stores all the information.

Databases that Liferay supports:

- **MySQL**
- DB2
- **Hypersonic**
- Oracle
- PostgreSQL
- SQL Server
- Sybase

</article>

<article id="quickStart">

## Liferay's Quick Start Guide

If you wanted to get Liferay up and running quickly, you can follow the following steps.  This is not necessary for the tutorial, but in case you wanted to see Liferay up and running quickly, you can use the bundle to get started.

#### 1. Get Java

We finished this step in [Before We Begin](/setup/before-we-begin.md), but in case you need to do it again, you may download and install **Java** in your environment by visiting <http://java.com> and choose your respective **Java JDK** version you wish to install on your operating system. Just follow the online instructions and verify if the Java has been successfully installed.

#### 2. Download Portal Bundle

Go to <https://www.liferay.com/downloads> and select "**Bundled with Tomcat**" and click the "**Download**" button.

#### Start Liferay Portal

1. Extract the downloaded bundle into some folder, e.g. `portal`.
2. Navigate to `/portal/liferay-VERSION/tomcat-VERSION/bin`
3. Execute `startup.bat` (on windows) or `startup.sh` (on Unix/lLinux/Mac OS X/GitBash).

	On Windows systems, the server console window will open.On \*nix systems and others, there is no output in console window as all logs are stored in `tomcat-VERSION/logs/catalina.out`. Keep watching it until you see something like:

	```
	INFO: Server startup in NNN ms
	```

Liferay Portal is now running and ready to be used. Upon start, the portal URL address (<http://localhost:8080>) will automatically be opened in your default browser.

(You can sign in using username: test@liferay.com and password: test).

#### Database Change

Your Liferay instance is currently using Hypersonic, an embedded database, to make installation fast and easy. This database should **not** be used in a production environment, so consider configuring Liferay to use a production-ready database available to you (MySQL, Oracle, etc).

</article>