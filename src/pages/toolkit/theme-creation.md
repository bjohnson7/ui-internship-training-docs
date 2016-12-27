---
description: "Theme Creation description."
icon: "image"
layout: "toolkit"
title: "Theme Creation"
weight: 4
---

<article id="guidelines">

## Guidelines

#### 1. Choose a theme you can get excited about

Take the time to find one that both strikes your fancy and isn't over your head. This will make the whole theme-building process more interesting and exciting for you.

**Resources:** [WordPress Themes](http://wordpress.org/themes/) and [Drupal Themes](https://drupal.org/project/Themes?page=1)

#### 2. Use the Liferay Theme Development Guide

Follow the directions laid out in the [Development Guide](https://dev.liferay.com/develop/tutorials/-/knowledge_base/7-0/themes-and-layout-templates). If there is an existing Liferay theme that has similar features to the theme you want to create, set that existing theme as the "base theme" for your new theme (see the `gulp extend` command on [this page](https://dev.liferay.com/develop/reference/-/knowledge_base/7-0/theme-gulp-tasks) of the Development Guide).

**Note:** You most likely won't be using Liferay Developer Studio to create your theme, so follow the directions that correspond to the terminal/Themes Generator.

#### Use the Theme Standards Guide

Reference the [Theme Standards](http://in.liferay.com/web/liferay-user-interface-design/wiki/-/wiki/Main/Theme+Standards) wiki page as you begin editing your CSS. This will save you from making a lot of obvious mistakes. You'll also want to review your code with these standards in mind before submitting it (i.e. sending a pull request) to your reviewer.

#### 3. CSS

Liferay uses [Twitter Bootstrap](http://getbootstrap.com/), [SASS](http://sass-lang.com/), and [Lexicon](http://liferay.github.io/lexicon/), and [Bourbon](http://bourbon.io/) for its CSS.
Familiarize yourself with these technologies after you have a general grasp on CSS.

**Note:** Only edit the `_custom.css` file in the `src` folder... for **ALL of your CSS**. When you create your theme there will be other categorized css files in the `build` folder (e.g. `_portlet.css`, `_layout.css`, etc.). However, all your CSS changes (including those made to portlets and layouts) will be made in your `_custom.css` file in your `src` folder.

**Tip:** Use Devtools and Firebug to fiddle with the CSS in your browser. It's much quicker than editing in the bundle if you want to test simple changes or additions (see the "Tip" in the "Other Resources" section of the [CSS Tutorial Page](http://in.liferay.com/web/liferay-user-interface-design/wiki/-/wiki/Main/Learn+CSS#section-Learn+CSS-Other+Resources).

#### 4. Restyle Portlets

When you create your theme, you'll likely need to restyle certain portlets (e.g. the login portlet or the search portlet). Each portlet has an ID that you can use to specifically apply styles in your `_custom.css` file. Here's [a list](https://dev.liferay.com/participate/liferaypedia/-/wiki/Main/Portlet+ID+Quick+Reference+Guide) of the portlets and their corresponding ID numbers.

#### 5. Create Your Own Layout

Don't shy away from creating your own layout. Don't try to simulate your desired layout using the `Nested Portlets` portlet. Creating your own layout is relatively simple, though it may be intimidating at first because you're required to work with an unfamiliar language (i.e. Freemarker/XML). It may be helpful to think of Freemarker as HTML remixed and souped-up. Follow the directions on the [Creating Liferay Layout Templates with the Theme Generator](https://dev.liferay.com/develop/tutorials/-/knowledge_base/7-0/creating-layout-templates-with-the-themes-generator-0) chapter of the Development Guide

**Note:** Again, you want to follow the directions for the Terminal, not Developer Studio). Keep in mind that in 6.2 Liferay uses [Bootstrap's "scaffolding"](http://getbootstrap.com/2.3.2/scaffolding.html), therefore instead of using `aui` classes you use `span`. For example, you use `span3`instead of `aui-w25`, `span6` instead of `aui-w50`, and columns with the class `portlet-column-only` needs an additional class of `span12`

**Note:** Remember to alphabetize your classes. Further, every `div class="portlet-layout"&gt;` needs an additional class, `row-fluid` (e.g. `&lt;div class="portlet-layout row-fluid"&gt;`).

#### 6. Format as You Go

Format your code as you write it. When writing code, it's tempting to just get all the code written down, and then go back and format it later. If you can, avoid doing this. It requires a little more front-end work to keep your code neat as you go along, but it saves a ton of time in the long run.

</article>

<article id="resources">

## Resources

- [WordPress Themes](http://wordpress.org/themes/)
- [Drupal Themes](https://drupal.org/project/Themes?page=1)
- [Development Guide](https://dev.liferay.com/develop/tutorials/-/knowledge_base/7-0/themes-and-layout-templates)
- [Theme Standards](http://in.liferay.com/web/liferay-user-interface-design/wiki/-/wiki/Main/Theme+Standards)
- [Twitter Bootstrap](http://getbootstrap.com/)
- [SASS](http://sass-lang.com/)
- [Lexicon](http://liferay.github.io/lexicon/)
- [Bourbon](http://bourbon.io/)
- [CSS Tutorial Page](http://in.liferay.com/web/liferay-user-interface-design/wiki/-/wiki/Main/Learn+CSS#section-Learn+CSS-Other+Resources)
- [Portlet IDs](https://dev.liferay.com/participate/liferaypedia/-/wiki/Main/Portlet+ID+Quick+Reference+Guide)
- [Creating Liferay Layout Templates](https://dev.liferay.com/develop/tutorials/-/knowledge_base/7-0/creating-layout-templates-with-the-themes-generator-0)

</article>
