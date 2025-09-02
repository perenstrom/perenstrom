# Exercise 4 – Git 2: Branching and Merging

_[Relevant section from the talk](https://github.com/perenstrom/talks/blob/main/2025-09-05-hyper-island-git/2025-09-05-hyper-island-git-3.pdf)_

- Create a new branch of your code and checkout with `git checkout -b my-feature-branch`
- You're now on a new branch of your code!
- Do a change to your readme file and commit it
- Switch back to the main branch with `git checkout main`, keep an eye on VS Code and see that it instantly updates the file to the state it is in on the main branch!
- Merge the feature branch into main (remember that you need to have the _recieving_ branch checked out) with `git merge my-feature-branch`
- Check the history of the repository with `git log --oneline`. You will see that the commit on your branch has just been added to the main branch, this was a so called fast forward merge.
- Create a new branch of your code and checkout with `git checkout -b my-feature-branch-2`
- Do a change to your readme file and commit it
- Switch back to the main branch with `git checkout main`
- Create a new file in the same folder, called text2.txt and add some text in it
- Add and commit the file
- Our two branches are now in two different states, one has a change in readme, and one has a completely new file
- Merge the new feature branch into main with `git merge my-feature-branch-2`
- This will now open up a primitive text editor (called vim, some people will get very angry with me calling it primitive, it is anything but) in your terminal indicating that git could not simply fast forward the main branch, but has to create a new merge commit. We have previously avoided this commit message editor when committing by using the `-m` option to set message directly. The first line of this text editor is the commit message, and any other lines can be used to add additional detail to the commit message, we can ignore those for now. Since this is an automated merge commit it will already have a message at the first line, we can stick with that default message.
- Quit the vim editor (and using default message) by typing `:q` and pressing enter (this is the most viewed question/answer on stack overflow, how to quit vim.)
- Our repository's main branch has now both the new file and the change we did in the readme file. To view a graphical representation of what we just did, use the command `git log --graph --oneline --decorate`, where you will see our two commits on our different branches, as well as the branches merging into one with a single merge commit (`q` to exit this view).
