# Exercise 6 – Git 4: Conflict Management

_[Relevant section from the talk](https://github.com/perenstrom/talks/blob/main/2025-09-05-hyper-island-git/2025-09-05-hyper-island-git-5.pdf)_

- Create a new branch from main called `my-feature-branch-4` and checkout
- Do changes on the first line in the readme file, and commit them
- Checkout the main branch
- Do different changes on the first line in the readme file, and commit them
- Checkout the feature branch
- Merge main into your feature branch to get the latest changes from main to your working branch, `git merge main`
- This will trigger a warning in your terminal saying that there's a merge conflict that needs to be managed, and that it couldn't automatically merge
- Look at the readme file in VS code, it will now have some other stuff in it that you didn't write, and VS Code will also helpfully color code it for us.
- You see both of your changes, first the change you made on your feature branch, and secondly – below the line of `=` – the incoming changes from main.
- Rewrite the line as you want it, incorporating both of your changes, or deciding that one of them is best (VS Code also provides helpful buttons above the conflict to automate this). If you do changes manually, make sure that the file when you save it only contains the text you want. I.e., remove the `<<<<<<< HEAD` and `>>>>>> main` lines, as well as the separating line, and any duplicate text you don't want to keep.
- Add and commit the readme file, this commit will be the merge commit
- The merge is now done and you can continue to work on your feature, or merge back into main.
- For this exercise, go ahead and checkout main, and merge your feature branch into main
