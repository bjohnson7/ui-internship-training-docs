---
description: "Keyboard Shortcuts description."
icon: "speedometer"
layout: "toolkit"
title: "Keyboard Shortcuts"
weight: 1
accentIndex: 0
---

<article id="usingShortcuts">

## Using Keyboard Shortcuts

The best way to learn keyboard shortcuts is to use them. There are plenty of lists and cheat sheets available online to help you learn them; therefore, the shortcuts listed below are merely some of the ones we found to be the most useful and/or obscure. For your convenience and exploration, we've also listed links to more exhaustive resources.

**Tip:** Force yourself to use keyboard shortcuts. The faster you become at navigating your computer, the more thought you'll be able to devote to creating and fixing things. Programmers love to use keyboard shortcuts, so chances are that if you're ever thinking "I wish there was a faster way to do this", well, there very well may be, so find and use that faster way.

</article>

<article id="generalTips">

## General Tips

- Liberate yourself from the right click when it comes to accomplishing simple tasks. Things like cutting, copying, pasting, and many other tasks have simple keyboard shortcuts. Don't waste your time using the right click if you don't need to.

</article>

<article id="windowsKeys">

## Windows 10

If you're an intern, you're likely using Windows 10. Therefore, we only address Windows commands on this page. Instead of repeating many of the basic shortcuts here that have already been tabulated on the [Understanding the Basics](/setup/understanding-the-basics.html) page, we urge you to use that page as a reference.

</article>

<article id="sublimeKeys">

## Sublime Text

|         Command         |                                                                                                                                                                                                        Action                                                                                                                                                                                                       |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `CTRL + [` / `CTRL + ]` | This decreases / adds an indent to the selected text by one tab space. This is especially useful when you add a single `<div>` to a file, and then have to indent 300 lines of code to preserve formatting                                                                                                                                                                                                          |
| `CTRL + D`              | Selects a character, word, or phrase and finds subsequent occurrences in the same file. For example, if you highlighted the word "_dog_", pressing `CTRL + D` would individually select each subsequent occurrence of the word "dog". This is very useful if you have to make broad changes to a specific word or phrase.                                                                                           |
| `ALT + F3`              | Does the same thing as `CTRL + D`, except it immediately selects all occurrences of the specified term on a page.                                                                                                                                                                                                                                                                                                   |
| `CTRL + L`              | Selects the entire current line.                                                                                                                                                                                                                                                                                                                                                                                    |
| `CTRL + SHIFT + T`      | Bring up the previously closed tab in Sublime Text.                                                                                                                                                                                                                                                                                                                                                                 |
| `CTRL + SHIFT + F`      | Find in Files. This feature is used frequently within Sublime and allows you to specify what folders are being searched. You can search all the files you have open in Sublime, all the files in a certain directory, or all the files on your computer. Be careful about running massive searches &mdash; it can crash Sublime and force you to restart the program before getting your search functionality back. |
| `CTRL + P`              | Goto Anything. This allows you to quickly navigate between files in a project folder. Simply type in the name of the file and you will be given a list of relevant options to choose from. For example, let's say you saw `StringPool.BLANK` in the code and you wanted to know what that evaluated to. You could type `CTRL + P` and then `stringpool` and you would be brought to the `StringPool.java` file.     |
| `CTRL + SHIFT + P`      | Command Palette. The Command Palette allows you to execute a variety of commands. You can type in an abbreviations, too. For example, if you type `sshm`, the first result will be `Set Syntax: HTML`, which tells Sublime Text that the file you are currently working on is an HTML file.                                                                                                                         |
| `CTRL + R`              | Go to Symbol. This lets you search the current file for where a method is declared. This is helpful when you have a large file and need to follow a chain of methods.                                                                                                                                                                                                                                               |
| `CTRL + F2`             | Bookmark. `CTRL + F2` will place a bookmark at the selected line while simply pressing `F2` will cycle through all the bookmarks in the file.                                                                                                                                                                                                                                                                       |
| `CTRL + SHIFT + V`      | Paste and automatically indent.                                                                                                                                                                                                                                                                                                                                                                                     |
| `CTRL + /`              | Toggle single-line comment.                                                                                                                                                                                                                                                                                                                                                                                         |
| `CTRL + SHIFT + /`      | Toggle block comment.                                                                                                                                                                                                                                                                                                                                                                                               |
| `CTRL + G`              | Go to line number.                                                                                                                                                                                                                                                                                                                                                                                                  |
| `CTRL + SHIFT + T`      | Bring up your previously closed tab.                                                                                                                                                                                                                                                                                                                                                                                |
| `CTRL + H`              | Find and replace.                                                                                                                                                                                                                                                                                                                                                                                                   |

**Additional resources:** [Sublime Text 3 Keyboard Shortcuts (Windows/Linux)](http://docs.sublimetext.info/en/latest/reference/keyboard_shortcuts_win.html)

</article>

<article id="devTools">

## Developer Tools (DevTools) / Firebug

|      Command       |                                                                    Action                                                                    |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| `CTRL + SHIFT + I` | Brings up developer tools in a web browser.                                                                                                  |
| `CTRL + SHIFT + C` | Initializes the inspector tool and DevTools at the same time. If DevTools is already open, then only the inspector tool will be initialized. |
| `ESC`              | Opens/Closes the console.                                                                                                                    |

**Tip:** Go to the settings for Google DevTools by pressing `CTRL + SHIFT + /`. there's a tab labeled **Shortcuts**, you'll find a thorough list of keyboard shortcuts. In Firebug, go to **Firebug Options** by clicking the Firebug icon in the top-left corner of the panel. In the dropdown menu, you should see an option titled **Customize Shortcuts**. Click on that and you'll be shown a complete list of keyboard shortcuts (which you can also edit to your liking).

**Additional Resources:**

- Chrome DevTools: <https://developers.google.com/chrome-developer-tools/docs/shortcuts>
- Firebug: <http://getfirebug.com/wiki/index.php/Keyboard_and_Mouse_Shortcuts>

</article>
