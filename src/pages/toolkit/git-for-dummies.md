---
description: "Git For Dummies description."
icon: "fork"
layout: "toolkit"
title: "Git For Dummies"
weight: 2
accentIndex: 1
---

[//]: # (TODO -- Need link to "Git Commands" page in #gitSummarized)
[//]: # (TODO -- Need link to "Initializing a Git Repository", "Git Workflow" pages in #gitWorkflow)

<article id="gitSummarized">

## Git Summarized

Git can be _incredibly confusing_ when you start using it. This guide has some great tips, but don't rely solely on it &mdash; feel free to look for Git tutorials on Google or YouTube. There are a lot of great beginner tips out there, and the faster you understand Git, the faster you can get up to speed with the rest of Liferay. It may take time, but it'll make sense eventually.

First off, you're going to have to use the command line. There are other means of going about using Git, such as SmartGit and GitGUI, but the command line is usually (but not always) the most effective way to use Git. A lot of Git is just learning to understand what you're seeing on the command line.

Git is best described as a "_**decentralized source control management system**_". That means that instead of having one `master` source that everyone has to work with (and that can be destroyed, shut down, corrupted, etc.) every user is given an independent copy of the master source code. They can make changes and then merge those changes back into the source repository (`upstream`). This main repository is called `trunk`.

What makes Git unique is that it only records the changes ("commits") made by individual users. So when a change is made, instead of having to upload thousands of files, whatever changes have been made are applied to the main repository, and the rest of the files are left untouched. It's like a painter adding onto a painting when he wants to make a change, as opposed to starting from scratch and making the change.

**Resources:**

- [Git Magic](http://www-cs-students.stanford.edu/~blynn/gitmagic/). The introduction may be especially helpful for gaining a basic understanding of what git, as a whole, is useful for.
- [Pro Git](https://git-scm.com/book/en/v2). Contains extensive documentation on how to use Git.
- [AVA Series](https://www.youtube.com/watch?v=sUQALbfDdAI&feature=c4-overview-vl&list=PL08C8894B4C602654) This is a great beginner video series on YouTube that is incredibly simple. It's made for absolute beginners, which most interns typically are.

In addition, see [this page](/NEED-LINK-TO-PAGE) for a list of most of the git commands you will need to use at Liferay.

</article>

<article id="gitWorkflow">

## Overview of Git Workflow

1. Setup a git repository (see [initialize a Git repository](/NEED-LINK-TO-PAGE))
2. Create a local branch to work on and make changes (see [Git Workflow](/NEED-LINK-TO-PAGE)
3. Add any new/modified files that you want to include in the commit
4. **Commit often** so it's easier to keep track of your work and changes
5. Push local commits to the remote repository
6. Submit a pull request

Tip: Check out [Debugging with Git](#debuggingWithGit) for an example of what your workflow would look like in Git while fixing a bug.

</article>

<article id="shortcutsAndTips">

## Git Shortcuts and Tips

Here are some helpful shortcuts for Git. If you haven't wrapped your mind around the basics of Git yet, you may want to study and use Git more before trying some of these shortcuts.

#### 1. Using Aliases

One of the things we recommend you do to improve your Git workflow is creating a `.bash_profile` with aliases. Aliases allow you to type custom, shorter commands in place of longer ones. To get started, create a file called `.bash_profile` in your `~` directory (Note: the tilde symbol, `~`, is equivalent to the file path of your home directory -- e.g. `C:\Users\liferay`). Let's say that you wanted to use the shorter string `cm` in place of `commit`. In your `.bash_profile`, you would include the line

```bash
alias cm="commit"
```

Now, you can use `git cm` instead of `git commit`. (You must close and re-open Git Bash for the changes to take effect.) You can also use aliases to represent non-git commands or even multiple, successive commands:

```bash
{literal}alias portal="cd ~/Desktop/Liferay/liferay-portal"alias up61x="git checkout 6.1.x; git pull upstream 6.1.x; git push origin 6.1.x"{/literal}
```

For an example of many of the things you can do with a `.bash_profile`, check out [Jon's configFiles](https://github.com/jonmak08/configFiles).

This is _optional_, by the way. In fact, it may even be more beneficial to navigate the long way for a while before you start setting up super shortcuts. However, you'll eventually want to start using them, because they significantly improve your workflow, allowing you to spend less time on busy work (i.e. typing in unreasonably long commands) and more time creating and fixing.

#### 2. .Gitconfig and Pull-Request Script

In your `~` directory, you'll also find a file called `.gitconfig`. Editing this file allows you to set more advanced options for Git. Here is a snippet of code from a sample `.gitconfig` file:

```bash
{literal}[user]	name = Your Name
email = your.name@liferay.com[core]
filemode = false
editor = 'c:/Program\ Files/Sublime\ Text\ 3/sublime_text.exe' -w   # makes Sublime Text rather than Vim the default text editor for operations such as interactive rebase[push]
default = matching   # when you run git push origin, all local branches are automatically pushed to their corresponding remote branches{/literal}
```

If you would like to be able to send pull requests from the command line rather than on GitHub, there is a Python script that allows you to do so (Note: See instructions for downloading and using this script). This script comes in handy when your desired reviewer doesn't show up in the GitHub pull-request GUI.

#### 3. Updating Branches and Repositories

There are two ways to update your local branches to reflect upstream changes. The first is by using `git pull --rebase upstream BRANCH`, which performs the entire process in a single step. The second, faster, way, is to use `git fetch upstream`, which pulls changes from all upstream branches but does not merge them. Since using fetch shows you all the branches that have changed, you can choose to update only those branches. The next step is to use `git branch -f BRANCH upstream/BRANCH`, which forces your local copy of `BRANCH` to be identical to its corresponding `upstream` branch. This operation executes instantaneously, unlike `pull --rebase`, which takes a little bit of time. Just make sure you always create local branches when you need to make changes and never make changes to your local copies of upstream branches, or else using `branch -f` will make your changes disappear.

#### 4. Using the "*" Operator

When there are several files that you have changed and you only want to stage some of them for commit, you can use `git add` with the `*` operator to select multiple files with similar file paths. Let's say that you run `git status` and get the following result, but you only want to commit the changes to the `bookmarks` and `document_library_display` portlets.

```bash
{literal}# Changes not staged for commit:#
#    modified:   portal-web/docroot/html/portlet/bookmarks/css/main.css
#    modified:   portal-web/docroot/html/portlet/document_library_display/search.jsp
#    modified:   portal-web/docroot/html/themes/classic/_diffs/css/color_schemes/dark.css
#    modified:   portal-web/docroot/layouttpl/custom/1_2_1_columns.tpl{/literal}
```

Simply run `git add portal-web/docroot/html/p *`, which will only add the two files in the `portlet` folder.

#### 5. Gitk

Finally, if you would like to see the commit history for a particular branch or see exactly which lines in which files you have changed, use gitk. This brings up an awesome Git GUI that will help you better visualize where your branches are, which changes you have staged for commit and which you have not, and more. Smart Git is an even more robust tool and it is particularly good for solving merge conflicts.

#### 6. Interactive Rebase

Interactive rebase is a very helpful feature of git that gives you the opportunity to easily alter a series of commits by rearraning the order, editing the messges, or squashing commits together into a single commit.

Running the command `$git rebase -i` will launch the text editor with a file listing the commits that will be rebased. To pick the last few commits in the current branch, use `$git rebase -i HEAD~n`, where `n` is the number of commits. For example, to rebase the last two commits

```bash
$git rebase -i HEAD~2
```

The file, `git-rebase-to`, will open up in the text editor and looks like the following:

```bash
{literal}pick 4a66600 Commit 1
pick 2566fcf Commit 2

# Rebase 617640f..2566fcf onto 617640f
#
# Commands:
#  p, pick = use commit
#  r, reword = use commit, but edit the commit message
#  e, edit = use commit, but stop for amending
#  s, squash = use commit, but meld into previous commit
#  f, fixup = like "squash", but discard this commit's log message
#  x, exec = run command (the rest of the line) using shell
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out{/literal}
```

##### Squashing/Merging Commits

1. Find the commits you want to squash/merge and run `$ git rebase -i HEAD~n`, where `n` is the number of commits you want to rebase

2. To merge the newer commits into the previous commit, change the `pick` command before each commit to `squash` or `s`

```bash
{literal}pick 4a66600 Commit 1
squash 2566fcf Commit 2{/literal}
```

3. Save and close the editor to begin rebase

4. Git will pause the rebase again after the merge is done and open the editor with the commit messages from all the commits. Edit the message if needed, save and close the editor to resume rebase.

##### Splitting Commits

1. Find the commit you want to split

```bash
$git rebase -i HEAD~n
```

2. Unstage the files

```
$git reset HEAD^
```

3. Add the files you want to stage for the commits and make commits

4. After you have made all the changes that you want, resume rebase

```bash
$git rebase --continue
```

To learn more about interactive rebase, go to <https://help.github.com/articles/interactive-rebase>.

#### 7. General Tips

The biggest thing to remember if you are just starting out with Git is just to be careful and patient. Always make a new branch (`git checkout -b <branchname>`) for the work that you are doing &mdash; if you always work in a separate branch there may be a little bit more overhead time, but if you screw up then you can easily fix it. If you send code off to be approved, don't touch it - if you need to work on it again, you'll get it back, or receive and okay to work on it again, don't risk conflicting with changes that a supervisor might make and then send to you by changing stuff in your specific copy that could conflict with someone else's. Don't ever try to "recreate" changes someone else made that you don't have access to, ask them for a pull request or get your hands on it the right way. Git can have a high degree of complexity as a whole, but you can make your little slice of things pretty simple, so don't make it harder on yourself.

</article>

<article id="debuggingWithGit">

## Debugging with Git

This is a conceptual walk-through. It won't cover every specific command, but it will detail a process that should help you better understand what is going on in Git and how to use Git for a simple bug fix. This is what a bug fix might look like for Liferay Portal (with a focus on how you would interact with Git):

1. Update our local copy of Liferay Portal

	First, we update our local copy of Liferay Portal to match Liferay Portal trunk (upstream on GitHub). This would ensure that all the changes that have recently been added to the trunk are reflected in your local copy (because you most likely won't want to be working off of an outdated version of portal). We would do this using a `git pull`. This would pull all the changes from Liferay Portal's source code onto our personal machine.

2. Create a new branch

	Second, we would make a new branch. This helps to preserve both the integrity of the master branch and the changes you've made to accomplish a specific task (just in case you need to refer to those changes in the future). For this example, we'll create a branch called `BugFix9`. All the changes we make will be made on this branch, but if all goes well, they will be merged into the master branch.

	**Note**: A good convention to follow is to include the ticket number in the branch name. For example, `LPS-12345-BugFix9`.

3. Make changes on your new branch

	Third, we would checkout our new branch and make our changes. Once our changes have been made, we would add them to our working tree, using a `git add`. This merely means that Git is now waiting to commit those specific changes we've added.

	**Note:** You'll likely make your changes in your bundle before making the changes to your branch in portal.

4. Rebuild portal with your bug fix

	Next, we rebuild our portal with the bugfix made to see if the fix really works (run `ant all` on your liferay-portal repository). This will help ensure that your bugfix isn't another bug in itself.

	**Tip:** Doing `ant all` on liferay-portal usually takes about 10 minutes. To save time from rebuilding all the source code in the portal, if you only make changes to a sub-directory (for example, portal-web), you can navigate to the sub-directory from the root with the command `cd portal-web` and do `ant compile deploy` instead of `ant all`.

5. Commit your changes

	Now, we're all finished and we've fixed our bug. All our changes have been added (another word for this is staged), and we're ready to commit them. This means that we're going to add them to the source code of our current branch. We run a `git commit`, and now the fixes we made are part of the branch `BugFix9`.

	**Note:** For bug fixes, we usually include the ticket number in front of the commit message. For example, `LPS-12345 Your commit message`.

6. Update your local branch

	Before we push our work to our origin, we need to update our local branch with `upstream/master` to make sure that all changes are compatible with the most recent changes on `upstream/master`. Check out [Sync new branch with upstream](/NEED-LINK) to see how to do that.

	Occasionally, this update and merging process does not go smoothly. If we changed the same part of the same file differently in the two branches that we are merging together, Git won't be able to merge them. Check out [Resolving Merging Conflict with SmartGit](#smartGit) to see how to resolve the conflicts.

7. Push your local branch to your origin

	However, we need to get these changes back to the Liferay Portal trunk. However, our changes will likely go through a reviewer (or two or three), so we'll push our branch to our origin and then send a pull request to a reviewer. We would do this by sending our local branch to our forked GitHub repository using `git push` (e.g. `git push origin BugFix9`).

8. Submit a pull request

	Last, we submit a pull request  to our reviewer (see [How to Submit a Pull Request to a Reviewer](/NEED-LINK)). If our code looks good, it will get pushed to Liferay Portal and become a part of the trunk.

	**Note:** When sending pull requests for bug fixes, another good convention to follow is to include the link to the JIRA ticket in the body section of the pull request.

9. That's it! We can go celebrate with juice and a game of ping-pong.

</article>

<article id="smartGit">

## Resolving Merging Conflict with SmartGit

A merging conflict occurs when we try to do a merge, rebase or cherry-pick operation while there are conflicting changes between two or more commits. If that happens, git will pause the merging process for us to fix the problem. In order to resolve the conflicts, we need to go through all conflicted files one bye one and modify them as needed. Below is a brief walk-through on how to use SmartGit's _Conflict Solver_ to resolve the conflicts.

1. Open SmartGit

2. Double click on the file with exclaimation mark (the exclaimation mark indicates a conflicted file) to open up the three-panel editor, Conflict Solver
​
	- The left panel shows what's new on the master. Usually these are the changes that we want to keep
	- The center panel is the working branch. This is where we select the changes that we want and make any further modifications if needed.
	- The right panel shows the changes we have made
3. Fix the conflict and stash the changes. Staging the file marks it as resolved in Git. Continue the process for the next conflicted file until there is no more conflicts
4. Now all the conflicts have been resolved, we run `$git rebase --continue` to continue the merging process

</article>



