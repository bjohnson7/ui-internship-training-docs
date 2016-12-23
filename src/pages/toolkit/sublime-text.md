---
description: "Sublime Text description."
icon: "code-file"
layout: "toolkit"
title: "Sublime Text"
weight: 3
---

###### Sublime Text is your best friend. After a while, it may be your only friend. And that's alright. Sublime has a ton of features that are indispensable for development. A few of these were mentioned above

<article id="projectManagement">

## Project Management

If you have a specific folder that has a number of files you are going to be examining, you can open the folder in your explorer, and simply drag-and-drop the folder into your Sublime Text. It will appear in a toolbar to the left of your text editor; this is the project manager. You can add multiple folders and directories to the project manager. A simple right-click on a desired folder or directory will bring up a number of options, including a search option that allows you to search the selected folder for keywords. This is especially useful when trying to track down a specific element. A double-click on a searched keyword in the "**Find Results**" page will bring up the relevant file in a separate tab.

</article>

<article id="packageControl">

## Package Control

Go to _Preferences &rarr; Package Control_ to download useful Sublime Text plugins. Exploration here is very valuable because there are a lot of things that you can find to make your life easier or just customize Sublime to your liking

(**Resource:** See how to [install](https://sublime.wbond.net/installation) and [use](https://sublime.wbond.net/docs/usage) Package Control).

Some useful packages:

- [Alignment](http://wbond.net/sublime_packages/alignment): Makes it easy to align multiple selections of text.
- [Githubinator](https://packagecontrol.io/packages/GitHubinator): This will allow you to right click on text in a Sublime Text file, and see the highlighted lines on GitHub's remote repository. Form there, you can do a Blame to determine the date and commiter of the last change to each line in the file, or view a History of all previous commits to a file.
- [LineEndings](https://github.com/SublimeText/LineEndings): Allows you to convert between Windows-style and Unix-style line endings.
- [WhoCalled](https://bitbucket.org/rablador/whocalled): Allows you to select a function and find all calls to that function in a project folder.
- [Side Bar Enhancements](https://packagecontrol.io/packages/SideBarEnhancements): Enhances the sidebar to have additional functionality upon right click of a file.
- [Bracket Highlighter](https://packagecontrol.io/packages/BracketHighlighter): True to its name, highlights brackets, which can be _very_ useful in some cases.

**Note:** You can also find packages that provide support for the syntaxes of various languages, such as ECO and Sass.

</article>

<article id="syntax">

## Syntax Highlighting

In the bottom right corner of your Sublime Text window, there's 2 indicators that specify what the tab size is set at, and what formatting is being applied to the open file (i.e. CSS, Javascript, etc.). Sometimes Sublime doesn't automatically apply the correct syntax styling, so use this menu to change how the file is displayed

</article>

<article id="userSettings">

## User Settings

Go to _Preferences &rarr; Settings - User_ to customize your Sublime Text experience. An example `Preferences.sublime-settings` file might look like this:

```
{literal}{
	"bold_folder_labels": true, // makes the sidebar more readable at a glance
	"color_scheme": "Packages/Color Scheme - Default/Monokai.tmTheme",
	"default_line_ending": "unix", // set the default line ending to Unix-style (Liferay only allows you to commit files with this type of ending)
	"draw_white_space": "all", // show a dot every time there is a white-space character
	"font_face": "Ubuntu Mono", // requires some work, but changes the font to something nicer
	"font_size": 11,
	"ignored_packages": [ "Vintage" ],
	"rulers": [ 80 ], // show a vertical bar at a distance of 80 characters from the left margin
	"tab_size": 4, // set tabs to be the same width as 4 spaces
	"translate_tabs_to_spaces": true, // use spaces to indent rather than tab characters
	"trim_trailing_white_space_on_save": true, // auto-delete trailing white space every time you save
	"word_wrap": true
}{/literal}
```

Some of the things in this sample file are very useful; having a ruler at 80 characters will help and setting tab size is always useful (the typical tab size is 4 spaces, although there are occasional exceptions).>

While most of these options are just personal preference, but `"trim_trailing_white_space_on_save"` should always be set to `true` and `"default_line_ending"` should always be set to `"unix"`.

For a complete list of settings, go to _Preferences &rarr; Settings - Default_. If you want to change anything, just copy it into your user preferences file and change the value.

Sublime is pretty customizable, so find a setup that you like and fill it up with all the crazy plugins or color schemes you can make use of (I recommend the color scheme Darkside by Dayle Rees, on that front).

</article>
