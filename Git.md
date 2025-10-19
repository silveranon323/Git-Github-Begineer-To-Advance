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
file3 will contain changes now of  1 and 2 mean the differences of both the files.
Now to apply changes
`patch file1 < file3.diff
will apply changes
(Till now we have seen existing methods to compare differences and fixing them).

## Version Control Systems.