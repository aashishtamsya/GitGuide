# GitGuide - How To Push Your Code & Files On Github

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
	-	[Graphical Clients](#graphical-clients)
	-	[Guides](#guides)

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

*	Perform a ` git init ` to create a new git repository.	

![git init](/Resources/gitinit.png)

## Checkout A Repository

*	Create a working copy of a local repository by running the command ` git clone /path/to/repository `.

*	When using a remote server, your command will be ` git clone username@host:/path/to/repository `.

## Git Workflow

Your local respository consists of three "trees" maintained by git.

*	The first one is your ` Working Directory ` which holds the actual files.

*	The second one is the ` Index ` which acts as a staging area.

*	Finally the ` HEAD ` which points to the last commit you've made.

![Workflow](/Resources/workflow.png)

## Add & Commit

*	You can propose changes (add it to the ` Index `) using ` git add <filename> `.

*	To add all modified files, ` git add * `.

*	This is the first step in the basic [git workflow](#git-workflow). 

*	To actually commit these changes use ` git commit -m "Commit message" `.

*	Now the file is committed to the ` HEAD `, but not in your remote repository yet.

## Pushing Changes

*	Your changes are now in the ` HEAD ` of your local working copy.

*	To send those changes to your remote repository, execute ` git push origin master `.

*	Change *master* to whatever branch you want to push your changes to.

*	If you have not cloned an existing repository and want to connect your repository to a remote server, you need to add it with ` git remote add origin <server> `.
	
*	Now you are able to push your changes to the selected remote server

## Branching

*	Branches are used to develop features isolated from each other.

*	The *master* branch is the "default" branch when you create a repository.

*	Use other branches for development and merge them back to the master branch upon completion.

![Branching](/Resources/branching.png)

*	Create a new branch named "*feature_x*" and switch to it using ` git checkout -b feature_x `.

*	Switch back to master ` git checkout master `.

*	And delete the branch again ` git branch -d feature_x `.

*	A branch is *not available to others* unless you push the branch to your remote repository ` git push origin <branch> `.
	
	

## Update & Merge

*	To update your local repository to the newest commit, execute ` git pull `.

*	In your working directory to *fetch* and *merge* remote changes. to merge another branch into your active branch (e.g. master), use ` git merge <branch> `.

*	In both cases git tries to auto-merge changes. Unfortunately, this is not always possible and results in *conflicts*. You are responsible to merge those *conflicts* manually by editing the files shown by git. After changing, you need to mark them as merged with ` git add <filename> `.
	
*	Before merging changes, you can also preview them by using ` git diff <source_branch> <target_branch> `.

## Tagging

*	It's recommended to create tags for software releases. this is a known concept, which also exists in SVN. You can create a new tag named 1.0.0 by executing ` git tag 1.0.0 <first_10_characters_of_commit_id> `

*	If your commit id is `  ` then command will be ` git tag 1.0.0  `, <10_characters> is the commit id on which you want to reference with your tag. You can get the commit id by looking at the [log](#log).

## Log

*	In its simplest form, you can study repository history using ` git log`.

*	You can add a lot of parameters to make the log look like what you required.

*	To see only the commits of a certain author, ` git log --authour=aashishtamsya`.

*	To see a very compressed log where each commit is in one line, ` git log --pretty=online`.

*	Or maybe you want to see an ASCII art tree of all the branches, decorated with the names of tags and branches, ` git log --graph --oneline --decorate --all `.

![Graph Log](/Resources/graph.png)

*	See only which files have changed, `git log --name-status`.

*	These are just a few of the possible parameters you can use. For more, see ` git log --help `.

## Replacing Local Changes

*	In case you did something wrong, which for sure never happens <smiley>, you can replace local changes using the command ` git checkout -- <filename> `.

*	This replaces the changes in your working tree with the last content in ` HEAD `.  Changes already added to the ` Index `, as well as new files, will be kept.

*	If you instead want to drop all your local changes and commits, fetch the latest history from the server and point your local *master* branch at it like this 

```git 

git fetch origin

git reset --hard origin/master

``` 

## Useful Hints

*	Built-in git GUI	-	` gitk `.

*	Use colorful git output	-	` git config color.ui true `.

*	Show log on just one line per commit	-	` git config format.pretty oneline `.

*	Use interactive adding	-	` git add -i`

## Links & Resources

### Graphical Clients

*	[GitX (L) [OSX, open source]](http://gitx.laullon.com/)

*	[Tower [OSX]](https://www.git-tower.com/)

*	[Source Tree [OSX & Windows, free]](https://www.sourcetreeapp.com/)

*	[GitHub for Mac [OSX free]](https://desktop.github.com/)

*	[GitBox [OSX, Appstore]](https://itunes.apple.com/gb/app/gitbox/id403388357?mt=12)

### Guides

*	[Think like a git](http://think-like-a-git.net/)

*	[Pro Git](http://progit.org/book/)

*	[Git Community Book](https://git-scm.com/book/en/v2)

*	[A Visual Git Guide](http://marklodato.github.io/visual-git-guide/index-en.html)

*	[GitHub Help](https://help.github.com/)