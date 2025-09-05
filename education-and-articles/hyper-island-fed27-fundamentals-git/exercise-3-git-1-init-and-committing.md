# Exercise 3 – Git 1: Init and Committing

_[Relevant section from the talk](https://github.com/perenstrom/talks/blob/main/2025-09-05-hyper-island-git/2025-09-05-hyper-island-git-2.pdf)_

In this exercise we will create our first Git Repository and do our first commits. We will also learn some commands to see what has changed in our files. Use the presentation PDF linked above as a reference for the different terms.

## Initializing a repository

1. In the folder we created in [the last exercise](./exercise-2-terminal.md), run `git init` to create an empty repository
1. Open VS Code and create a new file, enter some text in this file and save it in the folder we created in the terminal, as _readme.txt_
1. Back in the terminal, type `git status`

You will see that you have one "Untracked file"; our newly created _readme.txt_

## Tracking and committing

4. To start tracking that file, and add it to the stage, type `git add readme.txt` (or `git add .` to track and stage all changed files, in our case only one)
1. Commit this file as a version by typing `git commit -m "Add readme file"`, this will make a new commit, with the message "_Add readme file_", you can write anything as a message, but keep in mind what a good message is (remember the Will rule!).

## Renaming default branch

6. Now that we have a commit in our repository, we will rename the default branch name of `master` to the new standard `main` with the command `git branch -M main`
1. Type `git status` to check the status of the repository, it will now say that you have nothing to commit.

## Doing a change and seeing the diff

8. Go back to VS code and add a new line to your file, and change one of the existing sentences a bit.

> [!NOTE]
> If you have only your git folder open in VS Code will know that the file is in a git repository and show you coloured markers based on your uncommitted changes.

1. Run `git status` in your terminal, it will now say that the readme file is modified.
1. To see _what_ has changed in the file, type `git diff`

> [!NOTE]
> Sometimes this command will take over your whole terminal window, to quit this mode, press `q`. This does not always happen.

It will show that the first line is removed, and three new lines have been added.

11. If you type `git diff --color-words` you will get a diff where the changes are color coded, here you will see your actual change in the first line, and your newly added text

## Committing our changes

12. Commit the changes by adding then with `git add .` and `git commit -m "Change readme"`
1. View the history of your repository with `git log --oneline`

---

[<-- Previous exercise](./exercise-2-terminal.md) | [Next exercise -->](./exercise-4-git-2-branching-and-merging.md)
