---
description: "Bug Fixes description."
icon: "menu-content"
layout: "toolkit"
title: "Bug Fixes"
weight: 8
---

<article id="JIRA">

## JIRA

Liferay uses JIRA as its issue-tracking system to process bug tickets. To learn more about JIRA, go to <http://www.liferay.com/community/wiki/-/wiki/Main/JIRA>. Below is a brief overview on bug fixes.

- First, go to JIRA to get a list of bugs that need to be fixed.
- Go through the list and pick a bug that you are interested to work on. Read the description carefully and follow the steps provided to reproduce the bug. If you decide to work on this bug, you can assign the ticket to yourself (click "Assign to Me" on the toolbar below the ticket title) and start progress.
- After we have fixed the bug, we send a pull request to have our fix reviewed
- Go to JIRA and create a review request under workflow

</article>

<article id="multipleIE">

## Install Multiple Versions of IE

Sometimes, a bug may be browser specific, meaning that the bug only happens within a specific browser. It can be Firefox or Internet Explorer or a particular version of a browser. Therefore, it will be convenient to have different browsers and multiple versions of IE installed on your machine for testing purposes. Generally, you can only have one version of IE installed on your machine. One way to run multiple versions of IE on a single computer is by using a virtual machine.

[//]: # (The tutorial is a mp4 link...can we just link with an audio tag?)

For Windows PC, follow this [tutorial](/link-to-the-audio) to install virtual machines. Afterwards, you may need to edit your `portal-ext.properties` file as well. Add the following line, where `[COMPUTER NAME]` is the name you set during the setup process and `[IP ADDRESS]` is your computer's IP address.

```properties
virtual.hosts.valid.hosts=[COMPUTER NAME],localhost,[IP ADDRESS]
```

If you need to check your computer's name, go to _Control Panel &larr; System and Security &larr; System_, and it is listed on that page.

To find your IP address,  follow [these instructions](//support.microsoft.com/en-us/help/15291/windows-find-pc-ip-address).

For Mac, check out [VMware Fusion](http://www.vmware.com/products/fusion.html).

</article>

<article id="settingUpMySQL">

## Setting up MySQL for Portal

When you work on bug fixes, you will see that there is an environment specification (something that looks like this: Tomcat 7.0.25 + MYSQL5.0. 6.1.x GIT ID:6d6b8814da7c7295ed4cab8420e070793361f856) in the details section. The second parameter tells what database is in use when the bug is discovered. Liferay comes with a default database called "hypersonic" or HSQL. This database is not meant for production use. You need to change to a real database (for example, MySQL) if you need interaction with the database. You don't need to setup a different database if the bug does not use database. HSQL will be sufficient for most of the tasks you do in UI. This section shows you how to set up MySQL in the portal.

#### 1. Download and Install MySQL (<http://dev.mysql.com/downloads/>)

_**NOTE**: You can set the root password as empty by leaving the root password field blank while setting up._

#### 2. Set the Environment Path

- Navigate to _Computer &larr; Properties &larr; Advanced System Settings &larr; Environment Variables_
- Add MySQL path (for example, `C:\Program Files\MysQL\MySQL Server 5.6\bin`) to the `Path`variable
- Open up a command prompt and type `mysql -u root -p` and enter the root password that you have setup when setting up MySQL. If everything is set up correctly, you should see `mysql>` in the command line.

```sql
{literal}C:\Windows\system32>mysql -u root -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 1
Server version: 5.6.14 MySQL Community Server (GPL)

Copyright (c) 2000, 2013, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>{/literal}
```

#### 3. Create Database

- To create a database called `lportal:` (Note: don't forget the semicolon at the end)

```sql
mysql> create database lportal;
```

- If database is created sucessfully, you should see the name of the database you just created listed under Database when you do `mysql> show databases`;

```sql
{literal}mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| lportal            |
| mysql              |
| performance_schema |
| sakila             |
| test               |
| world              |
+--------------------+
7 rows in set (0.01 sec){/literal}
```

#### 4. Configure Database in Portal

Locate `portal-ext.properties` file in `tomcat\webapps\ROOT\WEB-INF\classes`

Add the lines below to setup MySQL

```properties
{literal}jdbc.default.driverClassName=com.mysql.jdbc.Driver
jdbc.default.url=jdbc:mysql://localhost/lportal?useUnicode=true&characterEncoding=UTF-8&useFastDateParsing=false
jdbc.default.username=
jdbc.default.password={/literal}
```

_Note:_

- Change `lportal` to the name of the database you created
- If you don't specify a username while setting up MySQL, the username is `root` by default. Append the username after `jdbc.default.username=`

Save the file and start tomcat. Look for the following messages when tomcat is starting:

```bash
{literal}INFO: Initializing Spring root WebApplicationContext
20:23:26,316 INFO  [localhost-startStop-1][DialectDetector:117] Determine dialect for MySQL 5
20:23:26,362 INFO  [localhost-startStop-1][DialectDetector:117] Found dialect org.hibernate.dialect.MySQLDialect
Starting Liferay Portal Community Edition 6.2.0 CE RC2 (Newton / Build 6200 / September 27, 2013){/literal}
```

Liferay portal should now be running with MySQL database!

</article>

<article id="gitBisect">

## Using Git Bisect

Git bisect is used to find the problem commit for regression bugs; bugs that were once fixed but have been re-broken. When a problem is discovered, it's not always clear that what modification cuased the regression. Sometimes it's easy to figure out, but in some cases, the only way to find out is by going back and testing each stage of the history to find out when the problem was introduced. However, checking each commit individually can take a significant amount of time, that's why we use Git bisect to help automate the process to find the problem commit. Git bisect uses binary search to look at all of the commits between good and bad commits, picks the middle one, and switches current head to that commit. It repeats the process until the problem commit is found.

In order to start Git bisect, you need to specify at least one good and bad commits. So we begin by finding a commit where things were working and another commit where things are not working. (Note: You can confirm a commit works or not by switching to that commit with `$git checkout` and rebuild the source code)

Start the bisecting process and specify the good and bad commits

```bash
{literal}$ git bisect start
$ git bisect good <commit hash>  (for exmaple, $git bisect good 123456)
$ git bisect bad <commit hash>{/literal}
```

Git bisect picks and switches to the middle commits between the specified good and bad commits. Mark the current commit as either good or bad using

```bash
{literal}$ git bisect good

OR

$ git bisect bad{/literal}
```

Continue the process until you reach the final commit. To end the Git bisect session, run

```bash
$ git bisect reset
```

For more information on debugging with Git, see [Git Tools - Debugging with Git](https://git-scm.com/book/en/v2/Git-Tools-Debugging-with-Git)

</article>