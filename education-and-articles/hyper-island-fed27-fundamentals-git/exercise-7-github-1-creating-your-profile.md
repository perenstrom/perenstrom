# Exercise 7 – GitHub 1: Creating Your Profile

_[Relevant section from the talk](https://github.com/perenstrom/talks/blob/main/2025-09-05-hyper-island-git/2025-09-05-hyper-island-git-6.pdf)_

In this exercise we will learn how to manage repositories in GitHub, and how to give and receive reviews of our code. We will do this by creating a profile page for ourselves on GitHub, this profile page will be visible to anyone that goes to your profile on GitHub. This exercise is by far the largest one in this section of the course, so let it take time to make sure you understand all steps. Use the presentation PDF linked above as a reference for how GitHub work, also use the previous exercises for commands learned in those exercises.

## Creating our profile repository

1. Go to https://github.com and create an account
1. Go to your repositories by clicking your avatar in the top right and going to Your repositories
1. Press the shiny green New button
1. To create a special repository for your profile, the repository name should be identical to your username, make sure it's set to public, and that "Add README" is checked (for coming repositories that aren't supposed to be your profile, the name can be anything)

## Creating a Personal Access Token

A Personal Access Token is a bit like a password that Git will use to communicate to GitHub.

5. Go to settings (click on your profile picture and select settings), and then to developer settings
1. Under Personal access tokens, select Fine-grained tokens
1. Press Generate a new token
1. Set a name for the token to remember what it is for, for example "Git in terminal"
1. Either keep the expiration date (the date when you need to renew the token for it to continue to work) or select a different expiration date (such as never).
1. Select that it should have access to all repositories
1. Under Permissions, press the Add permissions button and add "Contents" as a repository permission
1. Change the Contents access to "Read and write"
1. Save
1. Copy the token and store it in a safe place.

> [!TIP]
> I highly recommend using a password manager such as BitWarden to manage passwords and tokens.

Anyone that gets access to the token can access your repositories. As the text states on the page, you will **not** be able to see the token again (but can delete it).

## Cloning our repository

15. Navigate to the repository we created before (clicking your profile and selecting repositories and then clicking the repository)
1. In the green Code dropdown, copy the HTTPS repository URL
1. In your terminal, navigate to your home folder by typing only `cd` (or any other folder where you want the project to be)
1. Type `git clone https://github.com/my-username/my-username.git` (make sure to replace the web address with the one you just copied from GitHub)

This will create a folder and clone the repository from GitHub into that folder.

## Creating a `dev` branch

19. Navigate to the folder in the terminal with the `cd my-username` command (replace with your username)
1. Create a new branch called `dev` and checkout

> [!NOTE]
> The name `dev` is a common name for a branch for changes not yet finished.

## Writing the profile

21. In VS Code, open the folder that was created by the clone command, and update the `README.md` with a short description of yourself. This file is a markdown file (`.md`) so you can use any markdown formatting to style your text.

> [!TIP]
> If you want to add images to your profile readme, create a new folder in the same folder called `images` and add your images there. Then you can use relative paths to show the image according to the markdown image syntax: `![Description of image](images/my-image.jpg)`

22. Save your file and commit the changes to the repository

## Pushing the changes to GitHub

23. Push your local changes to the `dev` branch on the remote on GitHub (called `origin`) with `git push origin dev`

Here you will be prompted to enter your username and Personal access token we created before (not your login password).

> [!NOTE]
> When entering passwords in the Terminal, nothing will appear to be typed in, this is expected and for security reasons.

You should now see that it has been pushed to a new branch on GitHub called `dev`. And on GitHub, you should see your changes in the readme if you switch to the dev branch using the dropdown on the repository's Code page.

## Opening a Pull Request

Since this is your own private repository, you would normally just merge to `main`, or even commit directly on `main`. But as a learning exercise we will open a Pull Request (PR).

24. On your repository page, there should be a yellow banner that says "dev had recent pushes...", and a green "Compare & pull request" button. Press that.

> [!NOTE]
> If the banner doesn't show up, first make sure that you see your changes on GitHub in the dev branch. And if so, go to the Pull requests tab and press the "New pull request" button there

In the top of the Compare changes view, there will be two dropdowns specifying the _target_ and the _source_ branch. In our case they should be `main` and `dev` (with the arrow pointing at `main` since that's where we want our changes to end up).

25. Make sure the target and source branches are correct.

Below that you will see a list of commits made, and also all the code changes (the diff). The diff will look a bit more clean than the one we've previously looked at in the terminal.

26. Go ahead and press Create pull request, enter a title and a description (description is optional) and press Create pull request again

As said before, normally in this private profile repository you wouldn't ask for reviews, but when working together with other people on projects, giving and receiving code reviews is an essential part of collaboration.

Requesting reviews can only be done towards a user that is added as a collaborator to the project, but anyone with read access to the repository can give an un-requested review.

We'll skip adding a collaborator and instead ask for a review by turning to a classmate and ask them to go to your profile repository and opening up the PR (use your learning pair for the course if available, otherwise organize so that everyone gives one and receives one review).

27. Ask a classmate for a review.

## Reviewing someone else's Pull Request

In addition to requesting a review from a classmate, you should also have gotten a request to review from a classmate yourself. So let's do that now.

28. Go to the repository of your classmate either by entering the url manually, or searching for their username and going to their repositories, and the repository matching their username.
1. Go to the Pull request tab and click on the open PR in the list

Here you can read any description they have provided, look at the commits, and all changes.

30. Click the Files changed tab to see all changes.

In a normal code review, you might want to comment on a specific line that has changed. In that case you press the blue plus button that appears when you hover on the line you want to comment (it has to be a line that has changed) and add a comment to, or start, your review.

31. Press the green Review changes button in the top right
1. Enter a comment, select Approve, and press Submit review

Here you could choose to only comment, or even request changes, but let's go ahead and approve the PR.

33. Tell your classmate that you've given them an approval
1. Wait for your classmate to also approve your PR

## Merging the Pull Request

Back in your own repository, you should now see a checkmark in the timeline of the PR that your classmate reviewed and left an approval.

35. Press the Merge pull request button
1. Enter a Commit message for your merge and a description.

Best practice here is to have a descriptive title and additional information in the description, this makes it easy to follow the history of a project, to see when and why features were added.

37. Press Confirm merge.

If you are working on a temporary feature branch, it's often best practice to delete the branch afterwards. Usually only `main` and `dev` are branches that are long lived in projects.

In this case, if you want to keep doing changes to the profile, and experiment without it being public directly on your profile page on GitHub, let the `dev` branch stay around. Otherwise, go ahead and press Delete branch. You can always create a new branch called `dev` later.

38. Go to your profile by pressing the avatar in the top right and pressing Your profile

Your new profile text should now be visible on your profile page, congratulations! :tada:

---

[<-- Previous exercise](./exercise-6-git-4-conflict-management.md) | [Next exercise -->](./exercise-8-github-2-adding-your-personal-web-site.md)
