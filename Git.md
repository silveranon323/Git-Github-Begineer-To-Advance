# GIT

## Introduction

These are version control systems used to keep track of different versions of your code.
Helps us in easily rolling back in our code when mistakes happen

## Version control:-

#### 1. When we try to mange changes in its super important to have a detailed history of information of organisation configuration file.This lets the administratror see what was modified and when.Helps in future documentation.version control system allows us to keep changes to our files those can be code configuration image of whatever else we need to track.

#### 2. Keeping historical copies like we ocassionally create copies of work in case we wanted to go back to an earlier version.

## Diffing files

`diff file1 file2` : Shows difference between 2 file.
`diff -u file1 file2`: Shows differences in a more unified manner.
popular tools are `wdiff` highlights difference between words.

To help even more there are some graphical tools.
Some of them are:**meld,kDiffs,vlmdiff.**
Patch command:Applies the differences to original file.
`patch oldfile < newfile`
`diff -u file1 file2 > file3`
file3 will contain changes now of 1 and 2 mean the differences of both the files.
Now to apply changes
`patch file1 < file3.diff
will apply changes
(Till now we have seen existing methods to compare differences and fixing them).

## Version Control Systems.

- Keeps track of changes make to file.
- We can track who made change to the file.
- Collabration made easier.

"Regular file system keeps track of only recent data of file i.e most recent version"

- if we look vcs closer its just a stem that stores files , a vcs keeps track of all the different versions that we create as we save our changes.

- Vcs also provide mechanism to author why change is commited including bugs, tickets issue fixed by the changes.
- In vcs files are organised to repositories.
- Thousands of people can contribute to a single repository.
- **Version Control System can be like a time machine.**

## Why Git is powerful:-

- It is distributed vcs which means that each developer has a full copy of repository repositories can be used by as many developers needed.

**Linus Torvalds developed Git**

## Git:-

- Free open source vcs.
- Git can work as a standalone program as a server.
- This means you can use git on a single machine without even having network.
- Git client can also communicate with the server.

## Some terms you should know:-

**Repository**:-A central in which data is stored and managed.
**Commit**:- Collection of edit we are making at one time is called commit.

\*\*Linus Torvalds developed git in 2005 for better facilitating process of developing the Linux kerner with developers across the globe.

## First Steps with Git:-

Vcs tracks who made changes for this we have to tell the git who we are.
**Commands:-**
`git config --global user.mail "test@example.com"`
`git config --global user.name "My name "`

- Command to initialize git in current directory.
  `git init`:- git file will be created in that repository.

- git file will be created in that repository

- git init is used to initialize new directories.
- Area outside git directory is called the working tree.
  -It is the current version of your project. You can think of like a sandbox where we perform all operations or modifications we want.
- working tree contain all files currently tracked by git we have added a file in working tree now to make our git to track our file.
  Following command is used.

**Command**:- ` git add filename.extension`

Staging area :- A file maintained by git(Index).
that contains all of the information about what files and changes are going to go in your next commit.

**Command:-**to get some information about the current working tree and pending changes

`git status`

we can see that our new file is marked to be committed ,this means that our change is currently in "staging area" to get it commited we use command `git commit`.

- it opens a text editior where we can enter a commit message.

- its the simple descraption of what we did to the file.

## Sections of Git project:-

**Git directory:-**Contains history of all files and changes working Tree. Current state of project.

**Staging Area:-**Changes that we have been marked to be included in next commit.

when we operate an git files can be tracked or untracked.
Tracked files are parts of snapshot untracked files are not part of snapshot yet.

**A Git tracked file undergoes:-**

**Modified:-** We made all changes to file
not yet committed.

**Staging:-** changes made to the file are ready to be committed

**Committed:-** Change, committed.

It means a file tracked by git , will first be modified when we change it in any way.Then it becomes staged when we mark those changes for tracking finally it will get committed.

**Command:-**
`git commit -m "message"`
Summing up the work we did:-
1.Modified the file.
2.Added to the staging area.
3.Comitted to the changes.

Note: You can't commit with a empty commit message.

## The Basic Git Workflow:-

1.git init
2.git add
3.git commit -m ""

Anatomy of Git commit message :

a short description of the change , followed by one or more paragraph giving more details of the change if needed.

- Spend time in your documentation now it will definatly pay off later.

**Command: history of commits is found.**
`git log`

**output:** unrequesting used as identifier.

**command:** to check current user configuration.
`git config -L`

## Skipping the Staging Area:-

- First we make changes and then we commit those changes.

- If we know that current changes are the ones we want to commit , we can skip the staging step and go directly to commit
  we use -a flag to git commit command this flag automatically stages every file thats tracked and modified before doing commit letting it skip the git add.

## Getting more information about our changes:-

by default git log shows us the list:-

- commits message
- Author
- Date of change.

If we want to look what actual lines are changed in each commit to do.With this git log we can use the -p flag.
The p comes from patch because using the flag , gives the patch that created.

(Format is equivalent to the diff -u output that we saw on earlier video)

`git log -P`

Since it shows all commits by using show method.

(q exit)

show:takes commit id as parameter.

**Show:** takes commit id as paramter.

**command:-** stats of repo.

`git log --stat`

## Removing a file:-

**command:-**
`git rm filename`
`git commit -m "  "`

## Renaming a file

**command:-**
`git mv oldname newname`

**gitignore:-** inside this we specify which files to be ignored for current repo.
(Example automatically generated filename noise while cheating/tracking)

**command:- to see all file**
`ls -la`

`echo .DS_store > .gitignore.`

`git add .gitignore`

`git commit -m "added git ignore file."`

**Head:** is used to indicate what the currents checked out snapshot is.

Undoing,Changes made before commit.

**command:**
`git checkout filename`
change the file back to early committed state by using git checkout before it gets Stagged.

To reset stagged changes

**command:-**
`git reset HEAD filename`

_Amending Commits:-_

**command:**
`git --amend`

it allows us to modify and add changes to most recent commit.

(We can't use it in public repos.)

Avoid amending commits that have already been made to public

## Roll Backs:

- `git revert`: a new commit is created with inverse changes.
- this cancels/previous changes instead of making it as though the original commit never happen scenario.

- fixing your work before commit is good.What if its already committed .
- its time to roll back.

There are few ways to Roll back the commit in git .
Now focus on git revert:-

- It doesnot mean that undo it means it creates a commit that contains time inverse of all the changes made in bad commit inorder to cancel them.

- so git revert will create a new commit opposite of everything in the given commit.

- we can revert last commit using head alias that we mentioned .

- think of head as the pointer to the snapshot of current commit.

**command:-**
`git revert HEAD`

## Identifying a commit :-

we can target a specific commit by using its commit id.

commit id is 40 char long calculated by using "SHA1" algorithm.

"What this algorithm does is takes a bunch of data as input and produce a 40 char string "

- Cryptographic algorithms like SHA 1 are really complex.So we don't go ideas into what it means.

- Git uses these hashfunctions to gurantee the consistency of repo.

- computing hash keeps the
  data constant because its calculated from all the information that makes up commit that makes up a commit .

- computing hash keeps data consistant.
  because its calculated from all the information that makes up a commit.

the commit message dates author authors.

taken from snapshot of the working trees.
if someone intentionally corrupt some data git can use the hash to spot the corruption.

**command:-**
`git revert identifier`

## Advanced Git interactions undoing things branching and merging:-
