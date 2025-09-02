# Exercise 3 – Git 1: Init and Committing

- In the previously created folder, run `git init` to create an empty repository
- Open VS code and create a new file, enter some text in this file and save it in the folder we created in the terminal, as readme.txt
- Back in the terminal, type `git status`
- You will see that you have one "Untracked file", our newly created _readme.txt_
- To start tracking that file, and add it to the stage, type `git add readme.txt` (or `git add .` to track and stage all changed files, in our case only one)
- Commit this file as a version by typing `git commit -m "Add readme file"`, this will make a new commit, with the message "Add readme file", you can write anything as a message, but keep in mind what a good message is (remember the Will rule!).
- Now that we have a commit in our repository, we will rename the default branch name of `master` to the new standard `main` with the command `git branch -M main`
- Type `git status` to check the status of the repository, it will now say that you have nothing to commit.
- Go back to VS code and add a new line to your file, and change one of the existing sentences a bit. VS Code will know that the file is in a git repository and show you coloured markers based on your changes.
- Run `git status` in your terminal, it will now say that the readme file is modified.
- To see what has changed in the file, type `git diff`, this will take over the terminal window and show what has changed. It will show that the first line is removed, and three new lines have been added.
- Press `q` to go back to the terminal
- If you type `git diff --color-words` you will get a diff where the changes are color coded, here you will see your actual change in the first line, and your newly added text
- Press q to go back to the terminal
- Commit the changes by adding then with `git add .` and `git commit -m "Change readme"` \* View the history of your repository with `git log --oneline`
