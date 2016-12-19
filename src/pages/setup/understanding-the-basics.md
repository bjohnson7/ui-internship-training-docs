---
description: "Understanding the Basics description."
icon: "module"
layout: "setup"
title: "Understanding the Basics"
weight: 1
---

###### In this section, you will learn about keyboard shortcuts and commands. Whenever possible, use keyboard shortcuts to navigate and execute simple actions. The better and faster you are at navigating, the better and faster you can work. The easiest way to understand what each command does is to try them as you go along.

<article id="article-1">

## Command Line / Terminal

To launch the command line / terminal

### Linux / Mac

- Launch *Terminal*

### Windows

- Press _windows key_ + _r_ to open the Run window
- Type in _cmd_ and hit enter (or click OK)

</article>


<article id="learning-2">

## Commands

### Linux / Mac Terminal

|     Command      |                                                                                                 Action                                                                                                |                                         Example                                         |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| `ls`             | List all contents of a directory including hidden files                                                                                                                                               | `$ ls` => lists all folders in the current directory                                    |
| `cd [directory]` | Move to the specified directory                                                                                                                                                                       | `$ cd /Applications` => moves the console to /Applications                              |
| `cd`             | Changes the home directory                                                                                                                                                                            | `$ cd` => moves the console to home directory                                           |
| `cd ..`          | Moves one level up                                                                                                                                                                                    | `$ /Applications/TextEdit > cd ..` => $ `/Applications`                                 |
| `cd ../..`       | Moves multiple levels up, where each `..` indicates 1 level                                                                                                                                           | `$ /Applications/TextEdit > cd ../..` => $ `/`                                          |
| `cd /`           | Moves you to the root level of the drive                                                                                                                                                              | `$ /Applications/TextEdit/directory/ > cd` / => moves you directly to `/`               |
| `cd win(TAB)`    | Moves one level down, where `win` is the first three letters of the directory. Use TAB to scroll through all directories that begin with the same three letters. Hold `SHIFT + TAB` to reverse scroll | `$ /Applications > cd win(TAB)` => scrolls through all directories beginning with "win" |
| `ps -aux`        | List all processes running from all users. `-ux` will only list processes from the current user                                                                                                       | `$ ps -aux` => shows all running tasks                                                  |
| `kill -9 [pid]`  | Kill the specified process id (basically force quit for the command line)                                                                                                                             |                                                                                         |
| `ARROW UP/DOWN`  | Scroll through previously used commands                                                                                                                                                               |                                                                                         |

### Windows Command Prompt

|     Command      |                                                                                                 Action                                                                                                |                                                 Example                                                  |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| `~`              | Stands for your current user directory on your computer (i.e. a user profile -- most likely named *liferay* -- on your Windows machine)                                                               | `~\Desktop`                                                                                              |
| `dir`            | Stands for Directory. Use it at anytime to see a list of all folders in the level you're at                                                                                                           | `C:\> dir` => lists all folders in the `C:` directory                                                    |
| `d:`             | Type in another drive to go there                                                                                                                                                  | `C:\> d:` => moves the console to `D:`                                                                   |
| `cd [directory]` | Move into the specified directory                                                                                                                                                                     | `C:\> cd Program Files` => moves the console to `C:\Program Files`                                       |
| `cd ..`          | Moves 1 level up                                                                                                                                                                                      | `C:\Program Files> cd ..` => moves the console to `C:\`                                                  |
| `cd ..\..\..`    | Moves multiple levels up, where each `..` indicates one level                                                                                                                                         | `C:\Program Files\Common Files\Intel> cd ..\..` => moves the console 2 levels back to `C:\Program Files` |
| `cd \`           | Takes you to the root level of the drive                                                                                                                                                              | `C:\Program Files\Common Files\Intel> cd \` => moves the console directly up to `C:\`                    |
| `cd win(TAB)`    | Moves one level down, where `win` is the first three letters of the directory. Use TAB to scroll through all directories that begin with the same three letters. Hold `SHIFT + TAB` to reverse scroll | `C:\Program Files>cd win(TAB)` => scrolls through all directories beginning with "win"                   |
| `tasklist`       | Displays all currently running tasks                                                                                                                                                                  | `tasklist` => shows all running tasks                                                                    |
| `tskill`         | Task Kill. Kills processes                                                                                                                                                                            | `tskill java` => kills any java processes                                                                |
| `cls`            | Clears the console screen                                                                                                                                                                             |                                                                                                          |
| `ARROW UP/DOWN`  | Scrolls through previously used commands                                                                                                                                                              |                                                                                                          |
|                  |                                                                                                                                                                                                       |                                                                                                          |

### Windows 10 Key shortcuts

|    Keystrokes    |                                   Action                                  |
|------------------|---------------------------------------------------------------------------|
| WIN + E          | Opens File Explorer and gives you quick access to your drives             |
| WIN + R          | Opens the Run window. Type in `cmd` and it takes you to the command line  |
| WIN + D          | Shows desktop / restore windows                                           |
| WIN + Left/Right | Docks the current window to the left (or right)                           |
| WIN + Up/Down    | Maximizes / Minimizes the window                                          |
| WIN + SHIFT + Up | Maximizes the window vertically                                           |
| WIN              | Opens directly to the search bar for programs and files in the Start menu |

### Web Browsers

| Keystrokes |                 Action                |  Alternatives |
|------------|---------------------------------------|---------------|
| CTRL + W   | Closes browser tabs and windows       |               |
| CTRL + T   | Opens a new browser tab               |               |
| CTRL + R   | Refreshes the (browser/system) window | F5            |
| CTRL + TAB | Switch between browser tabs           |               |
| ALT + D    | Address bar                           | CTRL + L      |
| CTRL + +/- | Zoom in/out                           | CTRL + Scroll |
| CTRL + 0   | Return to default zoom state          |               |


### General Navigation

|          Keystrokes          |                 Action                |   Alternatives   |
|------------------------------|---------------------------------------|------------------|
| CTRL + W                     | Closes browser tabs and windows       |                  |
| CTRL + R                     | Refreshes the (browser/system) window | F5               |
| ALT + TAB                    | Switch between windows                |                  |
| SHIFT + ALT + TAB            | Reverse switch between windows        |                  |
| SHIFT + right click a folder | Extended folder/file menu             | SHIFT + menu key |
| CTRL + SHIFT + N             | Create a new folder                   |                  |
| F2                           | Rename folder                         |                  |
| ALT + D                      | Address bar                           | CTRL + L         |
| CTRL + ALT + DEL             | System menu                           |                  |
| CTRL + SHIFT + ESC           | Task manager                          |                  |

### Text Editing

|           Keystrokes           |                           Action                          |
|--------------------------------|-----------------------------------------------------------|
| CTRL + C                       | Copy                                                      |
| CTRL + X                       | Cut                                                       |
| CTRL + V                       | Paste                                                     |
| CTRL + Y                       | Redo                                                      |
| SHIFT + up/down                | Selects up to the line above or below where the cursor is |
| SHIFT + home/end               | Selects on the same line from where the cursor is         |
| CTRL + right/left              | Jumps whole words                                         |
| CTRL + SHIFT + right/left      | Selects whole words                                       |
| CTRL + backspace               | Deletes backward by word                                  |
| CTRL + del                     | Deletes forward by word                                   |
| CTRL + A                       | Select all                                                |
| CTRL + Z                       | Undo/revert                                               |
| TAB / CTRL + ]                 | Increase indent on current line/selected lines            |
| SHIFT + TAB / CTRL + SHIFT + [ | Decrease indent on current line/selected lines            |

</article>

