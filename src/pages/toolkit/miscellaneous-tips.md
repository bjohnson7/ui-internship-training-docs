---
description: "Miscellaneous Tips description."
icon: "pen"
layout: "toolkit"
title: "Miscellaneous Tips"
weight: 8
accentIndex: 0
---

###### This is anything you will probably encounter at some point that the Wiki doesn't address and doesn't fit into other categories of the Toolbox.

<article id="notes">

## A Note on Notes

Take notes. Get a notebook, sticky notes, napkins, etc. and take notes. What you learn today, you very well may forget tomorrow; or, you may forget in 20 minutes. Taking notes will help you pick up a lot of the concepts and commands much quicker, as well as helping to organize workflow and projects.

</article>

<article id="tips">

## General Tips

- Be sure to check your slashes in file names. Windows uses forward-slashes, but the rest of the world uses back-slashes.
- Adding spaces in file names is a hassle. Just don't do it. If you can't avoid it (you usually can), the way to type a space into a console such as GitBash is as follows:
	- To move through our `LiferayBundle` directory and then access the folder `Alloy UI`, you would have to type: `cd LiferayBundle/Alloy\ UI/`. Note the front-slash preceding the space.
- Never run an `ant all` or an `ant deploy` in your plugins repo. Always specify a folder.
- When deploying specific plugins, an `ant all` command can typically be used in lieu of an `ant deploy`, and is usually more effective and clean.
- Think about the way you are organizing your files. Create multiple bundles and use multiple copies of `liferay-portal` and `liferay-plugins` for every bundle you have. Here is a hint, separate your bundles and your core repositories. This way you can navigate them more clearly, this will also help you navigate your machine and bundles.
- If you are editing a file in the `portal-web` folder, you can make changes to the corresponding file in your bundle folder. This will allow you to view the results of your changes simply by refreshing the page rather than having to run `ant deploy` every time. For example, if you are working on `liferay-portal/portal-web/docroot/html/portlet/init.jsp`, the corresponding file can be found at `tomcat-7.0.40/webapps/ROOT/html/portlet/init.jsp`. Just be sure to apply your changes to the original file when you are done.
- Whenever you write code, make sure that it complies with Liferay's [source formatting guidelines](http://in.liferay.com/web/global.engineering/wiki/-/wiki/Core+Development+Main/Peer+Reviews+Checklist).
	- With regards to formatting - `ant format-source` is extremely useful, although it hates inline comments. Be careful and deliberate about it - step back and really look at the code and remove anything over complicated or superfluous. According to Liferay, _the code should be readable without comments_.
- Know your code- why everything is there, what it does, why it is needed. You are responsible for the code that you write, having that depth of knowledge forces you to make it good, and helps when you explain what you did. It also helps recognize stuff you can cut out when you format.

</article>