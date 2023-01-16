# Lab #1 - Getting Started with Git

In this lab, you will work through a series of exercises to improve your understanding of Git.  **The goal of this lab is to gain some proficiency with Git**.   In this lab you will:
1. Reviews some important commands and provides some resources for you to practice.  
2. Complete Git Katas to practice Git operations (but not on this repo).
3. Complete a number of operations on this repository for this lab and push the changes back to GitHub.   
4. Complete the Git review quiz.  You will have 3 attempts with the quiz.

This lab must be completed by the end of the day on Friday January 27th, 2023.

Before you get started, you will need to make sure that Git is installed on your local machine (lab machines should have Git installed): https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

**Clone this repo to your local machine before starting as you will need to use this repo to complete the lab assignment.**  

## What is Git?

Git is a VCS that is a collections of branches and tags (branches are also know as *heads*).  
* Git was designed to enable lightweight branching and merging.
* Each repository can have any number of branches.
* You don’t need to be afraid of making throwaway branches for
experiments.  You will merge branches back into your main branch that you will use. 

Remember that Git tracks the history of your whole project, not the history of
individual files.  Best practice is to keep projects that are logically separate in separate Git repositories.

Git is all about commits: you stage commits, create commits, view old commits, and transfer commits between repositories using many different Git commands. The majority of these commands operate on a commit in some form or another, and many of them accept a commit reference as a parameter. For example, you can use git checkout to view an old commit by passing in a commit hash, or you can use it to switch branches by passing in a branch name.  (see https://www.atlassian.com/git/tutorials/refs-and-the-reflog#:~:text=A%20ref%20is%20an%20indirect,git%20is%20usually%20called%20.git%20.)

You will often refer to *refs* when using git, but what is a *ref*?   A *ref* is a of referencing a commit (when you make a commit to your repo, it is referenced by an SHA-1 hash, which you can see in the output of your git log).   The *ref* is a user-friendly alias for a commit hash that can be used for representing branches and tags. 

 Every working copy has its own Git repository in the .git subdirectory (with arbitrarily many branches and tags).
The most important ref is **HEAD**, which refers to the current branch. The .git subdirectory also stores the **index** which is the staging area for changes on top of **HEAD* that will become part of the next commit. Finally, the files outside of .git are the working tree.   

When you are working with your repo, changes will be make to the working tree and be added to the index.   The index can be committed to the current branch, where it will become the **head**. (https://web.mit.edu/nelhage/Public/git-slides-2009.pdf)

## Git Commands

There are a number of Git commands that will be commonly used.   Take the time to review each command and understand what it will do (you will need to have an idea about these commands going forward).  This list is based off https://github.com/joshnh/Git-Commands.  You can also get details on Git commands at https://www.atlassian.com/git/glossary.

### Getting & Creating Projects

| Command | Description |
| ------- | ----------- |
| `git init` | Initialize a local Git repository.  It creates an empty Git repository in the current directory. By default it will have one branch named master.|
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository from the supplied *url*. This may be over HTTP, SSH, or the Git protocol, or it may be a path to another local repository  |

**Both of these operations will create a working copy.**  

### Basic Snapshotting

| Command | Description |
| ------- | ----------- |
| `git status` | Check status.  Display the files changed in the index and in the
working tree. |
| `git add [file-name.txt]` | Add a file to the staging area (from working tree into the index).|
| `git add -A` | Add all new and changed files to the staging area |
| `git commit -m "[commit message]"` | Commit changes out of the current index. |
| `git rm -r [file-name.txt]` | Remove a file (or folder) |

### Branching & Merging

| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote) |
| `git branch [branch name]` | Create a new branch |
| `git branch -d [branch name]` | Delete a branch |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git checkout -b [branch name]` | Create a new branch and switch to it |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it |
| `git branch -m [old branch name] [new branch name]` | Rename a local branch |
| `git checkout [branch name]` | Switch to a branch |
| `git checkout -` | Switch to the branch last checked out |
| `git checkout -- [file-name.txt]` | Discard changes to a file |
| `git merge [branch name]` | Merge a branch into the active branch |
| `git merge [source branch] [target branch]` | Merge a branch into a target branch |
| `git stash` | Stash changes in a dirty working directory |
| `git stash clear` | Remove all stashed entries |

### Sharing & Updating Projects

| Command | Description |
| ------- | ----------- |
| `git push origin [branch name]` | Push a branch to your remote repository |
| `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
| `git push` | Push changes to remote repository (remembered branch) |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git pull` | Update local repository to the newest commit |
| `git pull origin [branch name]` | Pull changes from remote repository |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` | Add a remote repository |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |

### Inspection & Comparison

| Command | Description |
| ------- | ----------- |
| `git log` | View changes (list the commits on the current branch) |
| `git log --summary` | View changes (detailed) |
| `git log --oneline` | View changes (briefly) |
| `git diff [source branch] [target branch]` | Preview changes before merging |
| `git show [object]` |  Show an object (e.g. the log information and patch for a commit, or the contents of a file). |



## Getting Some Practice with Git (But Not On This Repo!) ##

There are numerous playgrounds to help your practice with Git.  The goal is to make sure that you are comfortable with the operations and commands of Git.  

Visualizing Branching: https://git-school.github.io/visualizing-git/
Oh My Git! (Gamified Git Practice): https://ohmygit.org/
Learn Git Branching: https://learngitbranching.js.org/

There are also a series of Git Katas that have been put together (https://github.com/eficode-academy/git-katas).   With these exercises, you can clone this repo to your local machine or to Google Cloud shell (this will allow you to quickly clone, test and throw away any changes).   These exercises will allow you to work through some common challenges that people may encounter with Git (without having to break your own repo!).  The instructions are detailed and would suggest working through them in Google Cloud Shell.   I would **strongly** suggest that you complete the **Basic Katas** 1 through 12, 14, 16 and 17 as well as **Katas that solve standard problems**.  There are common activities and challenges that you will encounter.  Remember that *practice makes improvement*; with Git, you need to practice and thing carefully about what is happening with your actions  There is nothing that you need to show from these practices, but you will be responsible for knowing how to deal with the **Basic Katas**

Getting Started with Katas: https://github.com/eficode-academy/git-katas#readme
Overview of Katas: https://github.com/eficode-academy/git-katas/blob/master/Overview.md

## Your Activites ##

Now that you've have some significant practice, here's what you need to do for this lab.  Make sure to use the **CommandLine interface on your local machine** to complete this operations (don't use web-based commits as you need to learn and practice the Git commands).

1. Clone this repo to your local machine (I would **strongly** suggest using the commandline version of the shell).  (see https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)
2. Create a branch called *greeting* and switch to this branch and change to the `src` folder.   If you run `git status` what is the output of this and why? [1 mark]
4. Create a file called greeting.txt.  Add a message to the file. [1 mark]
5. Add `greeting.txt` files to staging area and commit (with appropriate message). [1 mark]
6. What is the output of `git branch`? Add the output of this to a file called branch.txt, add the file to staging and commit (with appropriate commit message).  [1 mark]
7. What is the output of `git log --oneline --graph --all`  (Just for your own learning)
8. Create a branch called *Readme* and switch to this branch (still in the src folder). [1 mark]
9. Create a `Readme.md` file using GitHub Markdown (https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).   Add some content using at least one header [+0.5], a list [+0.5], emphasis [+0.5] and a hyperlink [+0.5].  Add `Readme.md` to the staging area and commit (with the appropriate message). [+1]
10. Pull your changes upstream to GitHub.   
11. Create a PR (Pull Request) to merge both branches into the `master` branch (note: this is done on GitHub). [+1]
12. Review and merge the changes (both of these items should end up in the `src` folder on the `master` branch (there should be no conflicts as they are different files)  (note: this is done on GitHub).  [+1]

These steps are important to become familar with as we will be working with this flow on a regular basis.  

# Submission
Submit the link to your repository for lab #1 through Canvas.  Your TA will review and mark your repostiory on GitHub.  If you don't push the repo back there will be nothing to mark.  No other submision format will be accepted (zipping up your lab and trying to submit it will not be accepted; this lab is about learning to work witgh Git). 

Once you are done with pushing your repo upstream, complete the Git review quiz on Canvas.  


