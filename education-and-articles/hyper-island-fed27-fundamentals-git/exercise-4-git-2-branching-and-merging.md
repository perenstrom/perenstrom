# Exercise 4 – Git 2: Branching and Merging

_[Relevant section from the talk](https://github.com/perenstrom/talks/blob/main/2025-09-05-hyper-island-git/2025-09-05-hyper-island-git-3.pdf)_

In this exercise we will play around a bit with merging different changes in different branches. Use the presentation PDF linked above as a reference for the commands you need and some terminology, also use the previous exercises for commands learned in those exercises.

## Creating a new branch and committing some changes

1. Create a new branch of your code and checkout with `git checkout -b my-feature-branch`
1. You're now on a new branch of your code!
1. Do a change to your readme.txt file and commit it
1. Switch back to the main branch with `git checkout main`

Keep an eye on VS Code and see that it instantly updates the file to the state it is in on the main branch!

## Merging the branches with fast-forward

5. Merge the feature branch `my-feature-branch` into `main` (remember that you need to have the _receiving_ branch checked out first) with `git merge my-feature-branch`
1. Check the history of the repository with `git log --oneline`

You will see that the commit on your branch has just been added to the main branch, this was a so called _fast-forward merge_.

## Merging the branches with a merge commit

7. Create a new branch of your code and checkout with `git checkout -b my-feature-branch-2`
1. Do a change to your readme file and commit it
1. Switch back to the main branch with `git checkout main`
1. Create a new file in the same folder, called `text2.txt` and add some text in it
1. Add and commit the file

Our two branches are now in two different states, one has a change in readme, and one has a completely new file

12. Merge the new feature branch into main with `git merge my-feature-branch-2`

This will now open up a primitive text editor (_called vim, some people will get very angry with me calling it primitive, it is anything but_) in your terminal indicating that git could not simply fast forward the main branch, but has to create a new merge commit. We have previously avoided this commit message editor when committing by using the `-m` option to set message directly.

The first line of this text editor is the commit message, and any other lines can be used to add additional detail to the commit message, we can ignore those for now. Since this is an automated merge commit it will already have a message at the first line, we can stick with that default message.

13. Quit the vim editor (and using default message) by typing `:q` and pressing enter

[How to quit vim](https://stackoverflow.com/questions/11828270/how-do-i-exit-vim) is the most viewed question/answer on StackOverflow, since this is a bonkers way to quit a program.

Our repository's main branch has now both the new file and the change we did in the readme file.

## Viewing a graphical history

14. To view a graphical representation of what we just did, use the command `git log --graph --oneline --decorate`

You will see our two commits on our different branches, as well as the branches merging into one with a single merge commit (`q` to exit this view).

---

[<-- Previous exercise](./exercise-3-git-1-init-and-committing.md) | [Next exercise -->](./exercise-5-git-3-rebasing.md)
