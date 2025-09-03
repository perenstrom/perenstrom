# Exercise 8 – GitHub 2: Publishing Your Web Site To GitHub

_[Relevant section from the talk](https://github.com/perenstrom/talks/blob/main/2025-09-05-hyper-island-git/2025-09-05-hyper-island-git-8.pdf)_

In this exercise we will connect a newly created repository on GitHub to a new repository on our computer, containing your personal web site that you will be working on throughout the programme. We will learn how to push changes we are working on on our computer to GitHub, as well as automatically deploying (publishing) these changes to GitHub Pages. Use the presentation PDF linked above as a reference, also use the previous exercises for commands learned in those exercises.

## Creating an empty repository on GitHub

1. Go to your repositories in GitHub, and press the New button

If you want your web site to be at `your-username.github.io`, it must be called `your-username.github.io`, otherwise it can be named anything and will appear at `your-username.github.io/repository-name`

1. Name your repository
1. Make sure to have "add README" turned OFF

You will now land on an empty repository with some instructions on how to hook the repository up to your local code, we'll go through it here as well.

1. Copy the HTTPS url of the git repository from the blue area

## Initializing a repository locally

1. In your terminal, navigate using `cd` to the folder with your web page files you've created earlier in the course
1. Use the command `git init` to initialize a repository

## Adding all our files to Git

1. Add all files in the folder to the git repository with `git add .`
1. Commit your files with `git commit -m "add existing files"`
1. Change the default branch name to `main` with `git branch -M main`
1. Add the GitHub repository url as a remote (called `origin`) for your local repository with `git remote add origin https://github.com/your-username/repository-name.git` (make sure to substitute in your GitHub username), this is the url we copied before

> [!TIP]
> Here you might want to add a `README.md` file to the folder and add a description of what the repository contains (the `README.md` file is what's shown on GitHub when you go to the repository page)

1. Add and commit the readme file.

## Pushing the files to GitHub

1. Push your local changes (all your web site files) to GitHub with `git push -u origin main`

This command also maps the branch `main` on GitHub to your branch `main` locally, in theory they could be named different, but I've never come across that.

After this first map, you can push your changes with just `git push`, if you are on the `main` branch. If you create a new branch and want to push that, you will want to use the full command for that branch the first time.

1. Go to GitHub and see that all your web site files are listed in the repository page

## Publishing your web site

1. Go to the settings tab of the repository, and press pages in the left menu
1. Under the Branch heading, select `main` as the branch to deploy from

> [!NOTE]
> This means that only changes pushed to `main` will be visible on the site, allowing you to work in a separate branch and when you're ready merge to `main` and deploy the new version of the site.

In the dropdown next to it you can also chose a different folder in your repository to be the starting point of your site, if your `index.html` file is not in the root folder of your repository

1. Press save, and GitHub will automatically publish the site

> [!TIP]
> You can see this process under the Actions tab of your repository.

This will not take long, and if you refresh the pages settings page you will see a link to your newly published site.

**Congratulations on publishing your first personal web page! 🎉**

---

[<-- Previous exercise](./exercise-7-github-1-creating-your-profile.md)
