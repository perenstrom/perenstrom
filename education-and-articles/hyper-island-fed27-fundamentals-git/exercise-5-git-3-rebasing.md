# Exercise 5 – Git 3: Rebasing

_[Relevant section from the talk](https://github.com/perenstrom/talks/blob/main/2025-09-05-hyper-island-git/2025-09-05-hyper-island-git-4.pdf)_

- Create a new branch and checkout with `git checkout -b my-feature-branch-3`
- Do changes in the readme file and commit them, do another set of changes in the readme file and commit them as well
- Checkout the main branch
- Do some changes in the text2 file, and commit them
- Checkout the my-feature-branch-3 branch
- Your feature branch is now "behind", some changes has happened on the main branch that you would like on your branch as well. We could do a merge as the last exercise, where we merge main into our branch, instead we will do a rebase.
- Unlike merge, we want to have our feature branch checked out when we do the rebase, and specify which branch we want to rebase onto, so check out the feature branch
- Do a rebase with `git rebase main`, which will take our two commits on my-feature-branch-3, and apply them one after the other on top of the latest changes on main.
- Now our feature branch is up to date with main, and we can continue our work, or merge to main.
- For this exercise, go ahead and checkout main, and merge your feature branch into main

[<-- Previous exercise](./exercise-4-git-2-branching-and-merging.md) | [Next exercise -->](./exercise-6-git-4-conflict-management.md)
