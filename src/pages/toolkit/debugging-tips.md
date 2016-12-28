---
description: "Debugging Tips description."
icon: "eye"
layout: "toolkit"
title: "Debugging Tips"
weight: 5
accentIndex: 4
---

###### Throughout the internship, you will find yourself working with code that doesn't do what you want it to do, and you'll wonder why. Instead of blankly staring at the code, follow these tips to make the process of debugging easier.

<article id="followTheChain">

## Follow the chain.

For example, maybe an error message is appearing in a portlet when it shouldn't be (for example, `A user with that OpenID already exists.`). Use Sublime Text to search for that string in the `liferay-portal` repository. You will find it in several `Language_*.properties` files, indicating that it is being translated from English to other languages. The underlying property name is `a-user-with-that-open-id-already-exists`. Now search for this string and ignore all the results in `Language_*.properties` files. You'll see, in a file called `open_id.jsp`, that this message is displayed when a `DuplicateOpenIdException` occurs. What causes a `DuplicateOpenIdException` to be thrown? Search for `throw new DuplicateOpenIdException`. You'll find the answer in `UserLocalServiceImpl.java`. A similar technique can be used to locate the file in which a particular view of a particular portlet is being generated. Just look for a rare string and search for it using Sublime Text.

</article>

<article id="searchForDefinitions">

## Search for a Function Definition

Along the lines of the last point, if you see a call to a function and think the bug you're looking for is occurring in that function, search for the function definition. If you're looking at a function definition and know that the file with the bug in it must be using that function, search for all calls to the function (or use the WhoCalled plugin for Sublime Text).

</article>

<article id="printStatements">

## Use Print Statements

If you are debugging a JavaScript file and want to know the value of any variable or expression at any point in the code, use `console.log()`. This will print the value of the expression to the Console tab of your Developer Tools. In a `.java` file or a Java block of a `.jsp` file, a `System.out.println()` statement will print to the Git Bash terminal in which you are running Tomcat. Outside of a Java block of a .jsp file, you can print directly to a portlet by enclosing an expression in a block surrounded by `<%=` and `%>` tags.

</article>

<article id="useTheBrowser">

## Use the Browser's Console to Debug and Test Code

If you declare a JavaScript variable as a window variable (for example, by saying `window.numColors = 2;` instead of `var numColors = 2;`), you can access this variable by typing its name in the console. Just be sure to remove all declarations of window variables in the final version of your code. If this variable has a function available to it, say `toString()`, you can get the function definition by typing `numColors.toString`, or you can get the result of a function call by typing `numColors.toString()`. More generally, you can use the console to test your own snippets of code before using them.

Again, _**don't be afraid to ask for help**_.

</article>