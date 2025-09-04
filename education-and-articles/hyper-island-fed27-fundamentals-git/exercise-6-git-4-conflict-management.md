# Exercise 6 – Git 4: Conflict Management

_[Relevant section from the talk](https://github.com/perenstrom/talks/blob/main/2025-09-05-hyper-island-git/2025-09-05-hyper-island-git-5.pdf)_

In this exercise we will do some merge conflict management. That is, decide what to to with files that has changed in multiple branches where Git cannot automatically determine what it should choose. Use the presentation PDF linked above as a reference, also use the previous exercises for commands learned in those exercises.

## Setting up for conflict

1. Create a new branch from main called `my-feature-branch-4` and checkout
1. Do changes on the first line in the readme file, and commit them
1. Checkout the `main` branch
1. Do different changes on the first line in the readme file, and commit them

Our readme file has now had two different changes to the same line, which are in conflict with each other

## Resolving the conflict

5. Checkout the feature branch
1. Try to merge `main` into your feature branch to get the latest changes from main to your working branch, `git merge main`

This will trigger a warning in your terminal saying that there's a _merge conflict_ that needs to be managed, and that it couldn't automatically merge.

Look at the readme file in VS Code, it will now have some other stuff in it that you didn't write, and VS Code will also helpfully color code it for us.

You see both of your changes, first the change you made on your feature branch, and secondly – below the line of `=`s – the incoming changes from `main`.

7. Rewrite the line as you want it, incorporating both of your changes, or deciding that one of them is best (VS Code also provides helpful buttons above the conflict to automate this).

If you do changes manually, make sure that the file when you save it only contains the text you want. I.e., remove the `<<<<<<< HEAD` and `>>>>>> main` lines, as well as the separating line, and any duplicate text you don't want to keep.

8. Add and commit the readme file as usual, this commit will be the merge commit

The merge is now done and you can continue to work on your feature, or merge back into `main`.

## Cleaning up

9. For this exercise, go ahead and checkout `main`, and merge your feature branch into `main`

---

[<-- Previous exercise](./exercise-5-git-3-rebasing.md) | [Next exercise -->](./exercise-7-github-1-creating-your-profile.md)
