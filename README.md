# HOW TO PUSH YOUR CODE ON GITHUB

A simple guide for getting started with git. No crap and deep-shit!

# Content
-	[Setup](#setup)
-	[Create A New Repository](#create-a-new-repository)
-	[Create A New Repository](#create-a-new-repository)
-	[Checkout A Repository](#checkout-a-repository)
-	[Git Workflow](#git-workflow)
-	[Add & Commit](#add-&-commit)
-	[Pushing Changes](#pushing-changes)
-	[Branching](#branching)
-	[Update & Merge](#update-&-merge)
-	[Tagging](#tagging)
-	[Log](#log)
-	[Replacing Local Changes](#replacing-local-changes)
-	[Useful Hints](#useful-hints)
-	[Links & Resources](#links-&-resources)

## Setup

*	[Download git for OSX](https://git-scm.com/download/mac)
*	[Download git for Windows](https://git-scm.com/download/win)
*	[Download git for Linux](https://git-scm.com/download/linux)
*	[Download git for Solaris](https://git-scm.com/download/linux)

## Create A New Repository

*	Create a new directory.
*	Open it using this command in terminal. 
```sh
$ cd /path/to/directory 
```

*	Perform a `git init` to create a new git repository.	

## Checkout A Repository

*	Create a working copy of a local repository by running the command `git clone /path/to/repository`
*	When using a remote server, your command will be `git clone username@host:/path/to/repository`

## Git Workflow

Your local respository consists of three "trees" maintained by git.

*	The first one is your `Working Directory` which holds the actual files.
*	The second one is the `Index` which acts as a staging area.
*	Finally the `HEAD` which points to the last commit you've made.

## Add & Commit

*	You can propose changes (add it to the `Index`) using 

```git
git add <filename> 
```

*	To add all modified files,

```git
git add *
```

*	This is the first step in the basic [git workflow](#git-workflow). 

*	To actually commit these changes use `git commit -m "Commit message"`

*	Now the file is committed to the `HEAD`, but not in your remote repository yet.

## Pushing Changes

*	Your changes are now in the `HEAD` of your local working copy.
*	To send those changes to your remote repository, execute `git push origin master`
*	Change *master* to whatever branch you want to push your changes to.
*	If you have not cloned an existing repository and want to connect your repository to a remote server, you need to add it with 

```git

git remote add origin <server>

```

*	Now you are able to push your changes to the selected remote server


## Branching

*	Branches are used to develop features isolated from each other.
*	The *master* branch is the "default" branch when you create a repository.
*	Use other branches for development and merge them back to the master branch upon completion.

*	Create a new branch named "feature_x" and switch to it using

```git

git checkout -b feature_x

```

*	Switch back to master

```git

git checkout master

```

*	And delete the branch again

```git

git branch -d feature_x

```

*	a branch is *not available to others* unless you push the branch to your remote repository

```git

git push origin <branch>

```

## Update & Merge

*	To update your local repository to the newest commit, execute

```git

git pull

```

*	In your working directory to *fetch* and *merge* remote changes. to merge another branch into your active branch (e.g. master), use

```git

git merge <branch>

```

*	In both cases git tries to auto-merge changes. Unfortunately, this is not always possible and results in *conflicts*. You are responsible to merge those *conflicts* manually by editing the files shown by git. After changing, you need to mark them as merged with

```git

git add <filename>

```

*	Before merging changes, you can also preview them by using

```git

git diff <source_branch> <target_branch>

```




## Tagging

## Log

## Replacing Local Changes

## Useful Hints

## Links & Resources
