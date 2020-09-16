# A simple crash course for getting started with Git

Git is a system for managing history and versions of a project, mainly code. This crash course focuses on the basic terms to get you up and running, without delving deeper into the more complicated bits.

## Installing Git
You can check if you have Git installed by going to your terminal/command prompt/powershell and typing `git --version`. If you get a version number, you've got Git.

### Linux
If you run Linux, your distro might include Git by default. If not, you can check out the information on [Git's own site for linux installation](https://git-scm.com/download/linux).

### Mac
You can get Git for Mac either if you've installed Xcode, or Homebrew. Follow the instructions at [Git's own site for Mac installation](https://git-scm.com/download/mac).

### Windows
The easiest way to get started with Git for Windows is going to https://gitforwindows.org/ and downloading their installer. That will give you Git, Git Bash (a bash emulator which you will use instead of the command prompt and will make following guides easier), and Git GUI (a graphic interface for Git, more on that later).

## Create your first git Repository
A Git **Repository** is the box where your project lives. Multiple repositories can be linked to eachother, more on that later.

Go to your terminal (I will use the term _terminal_ for both Mac, Linux and Windows, on Windows I suggest using Git Bash) and navigate to your project folder.

Type the command `git init`, this will create an empty Git repository for your project.

## The Git workflow
A normal Git workflow is
1. Do some changes to your files
1. Mark the files as ready, or **stage** them, to be added to the repository
1. Add the files to the repository, or **commit** them, creating a new fixed point in the history of your project

Let's go through those last steps.

### Staging files
When you have made some changes to your files, Git knows about this. If you type `git status` you will get a list of changed files that has not been commited yet. You can chose which files you want to commit, perhaps you've changed multiple files, but only one is ready to be commited.

To **stage** your files, you type `git add ` and then your filename. Most times you want to stage all changes, which is indicated by a dot: `git add .`.

### Commiting files
When you're ready to create a new point in the history of the project, you **commit** the files you have staged. A commit is a list of changes made to the files, along with a message.

You commit your staged files by typing `git commit -m Your message here`. Commit messages should be short and descriptive to what changes you have made. 

You have now created a version of your project that you can go back to at any time.

## Linking multiple repositories, mainly your computer and the cloud

The power of Git lies in its portability. Sure, it's nice to have a history of changes in your project locally on your computer. But if your computer crashes, everything is gone. If someone else joins you on your project, they can't access the code on your computer.

To solve this, we link repositories together. The most common cloud service to host repositories is GitHub. When you link a local repository on your computer to a repository on GitHub, you usually consider the version on GitHub to be the 'real' version, especially if you are multiple people working on the same project.

The process of linking repositories is usually
1. Create an empty repository to be linked (usually on GitHub)
1. Point your local repository to the one on Github

### Create a repository on GitHub
Creating a repository on GitHub is very easy. Make sure you've created an account, and then just press the green button marked 'new' on the left side of your dashboard. Select a suitable name for your repo, and chose if it should be public or private. If you have created a local repository already, make sure to not check any of the checkboxes, and then create your repository.

Now you should land on your fresh repository page on GitHub, where GitHub will provide you with a command to type to link your local to the GitHub one. It should look something like `git remote add origin https://github.com/your-username/your-repository-name.git`. When you type that into your terminal, your local repository will get a **remote repository** linked to it.

## Extending your Git workflow to the remote repository
Now that you have a linked repository on GitHub, you have to add a few steps to your workflow. It will now be

1. Do some changes to your files
1. Mark the files as ready, or **stage** them, to be added to the repository
1. Add the files to the repository, or **commit** them, creating a new fixed point in the history of your project
1. Repeat 1-3 until you want to save your commits in the cloud.
1. (**Pull** any changes someone else made to the repository on GitHub)
1. **Push** your changes to the remote repository

### Pulling changes from the Remote repository
If you're working in a team, where someone else also can make changes to the code, it is always best to download – or **pull** – their changes to your local repository before adding your own. If you only work by yourself, this is probably not needed.

### Pushing your changes to the Remote repository
When you feel ready to save your **commits** to the remote repository on GitHub, you upload them – or **push** them. You do this by typing `git push -u origin master`.

## Graphical tools to make the process easier
Even though Git is a command line tool, there are a lot of graphical tools that make this process a lot easier to grasp. Git GUI for Windows, GitKraken, SourceTree, GitHub GUI, to name a few. My personal preference is GitKraken, which has a limit in the free version that it's not able to handle private repositories though.

In most of these programs, you can see a list of changed files, press a button to stage them, and then type your commit message and press a button to commit. And then press the push-button to push them to GitHub. You can also see all your changes in a long list.

## Cloning a repository
If you for some reason need to start working on your project on a new computer you don't need to initialise a repository again. You then just need to clone the repository from GitHub to your local computer. The graphical tools make this very easy.

## Going further
The above information get's you up and running with Git and is all you need for basic version management of your project. Here are some terms and concepts you might encounter when you get more advanced.

### Branches
A very useful tool when developing is using different **branches** of your code to separate different features being developed on. A common pattern is to have the main branch (usually called _master_) only contain code that is "production ready", that is fully functional to be run live on a server, or sold on an app store. In addition to that you usually have a branch called _develop_, where you can do your development and test new functionality.

These are usually good enough for simple projects. Bigger projects often also use _feature branches_. These contain new features currently being developed, keeping them in a separate branch can be good when working on multiple features at the same time. This will also provide clear history when **merging** branches together when a feature is complete.

### Merging
When two branches need to become one they are **merged**, either when a feature is done and its _feature branch_ should enter the _develop_ or _master_ branch, or during the development of a feature when other changes made to the _develop_ branch should be merged into the _feature branch_ to keep it up to date with other changes that has happened.

### Merge conflicts
Sometimes when to branches are merged, you will encounter a **merge conflict**. This is when the same file has been changed in both branches. Git is really smart and can usually merge files without problems, but sometimes a real human is needed. It is then up to you to compare the file in both branches and chose which changes, or both, to keep.
