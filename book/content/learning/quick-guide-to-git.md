# 3.1. Git - A Quick Guide

This is supposed to be a quick reference guide to using Git. It is not meant to be comprehensive. For a good understanding of Git, I would highly recommend the freely available [Pro Git book](https://git-scm.com/book/en/v2). The book is an excellent resource not just for beginners, but also for advanced users who can use it as a reference to understand what goes on under the hood.

## What does Git do and why use it?

Very simply put, Git keeps track of changes in your code. Well, it actually [takes snapshots](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F) of your code at every change. 

Why is that useful? Think of it this way: you have a project that you are working on. You make some changes to the code and it works. You make some more changes and it breaks. You want to go back to the version that worked. You can do this manually by saving different versions of your code in different files, but this can get messy very quickly. Git helps you keep track of these changes and helps you go back to the version that worked. Nice to have a safety net, right?

But Git is not just about **going back in time**. You can also **work on different branches** of the same codebase in parallel. This is very useful when you want to try out new features without breaking the main codebase. You can also **collaborate smoothly with others** and everyone can make their own changes. Git helps you keep track of who did what and when. It also helps you merge your changes with others' changes. 

The more you use it, the more you will come to appreciate its power and simplicity. I've been using Git for over 5 years now and am still amazed every now and then at how much it can do. 

So, let's get Git going on our computer then...

## Get Git to work on your machine

1. Check if you already have git installed on your machine by running the following command:

`````{tab-set}
````{tab-item} Windows
Open Command Prompt and run the following command:
    
```bash
git --version
```

````

````{tab-item} MacOS / Linux
Open Terminal and run the following command:

```bash
git --version
```

````
`````

2. If you don't have git installed, you can download it from the [official website](https://git-scm.com/downloads). Check if your installation worked by running the commands in Step-1.

3. Once you have Git installed, you need to configure it. Run the following commands in your terminal / command prompt:

```bash
git config --global user.name <your-name>
```
    
```bash
git config --global user.email <your-email-id>
```

Replace `<your-name>` and `<your-email-id>` with your name and email address. This information will be used to identify you in the commit history. If you don't do this, Git will prompt you to do this when you try to commit changes.

## Working with Git regularly

### Why work locally and not work directly with Github on browser?

Working locally using Git instead of directly on GitHub through the browser provides several practical advantages that make it a preferred approach for many developers.

Working locally allows you to make changes, test code, and track progress without needing an internet connection or waiting for uploads to a remote server. Since Git operates as a distributed version control system, all project history and tools are available on your local machine. This makes tasks like creating branches, committing changes, and exploring the history much faster compared to working directly on a browser-based platform.

One of the key benefits of working locally is the ability to continue progress even when you are offline. Whether you’re traveling, working in an area with limited connectivity, or experiencing internet issues, you can still write code, commit changes, and manage your project without interruptions. Once you’re back online, you can sync your work with GitHub.

A local environment provides a private space where you can experiment freely without immediately sharing your work. You can test new ideas, make mistakes, and iterate on your code without affecting the main project or exposing incomplete work to collaborators. This flexibility ensures that only polished and reviewed changes are shared when you push updates to GitHub.

Using Git locally allows you to take full advantage of version control features such as branching and committing. You can create branches to work on specific features or fixes independently from the main codebase. Commits let you save snapshots of your progress at different stages, making it easy to track changes or revert to earlier versions if needed. These tools help maintain an organized workflow and reduce the risk of losing important work.

While working locally gives you control over your development process, GitHub serves as a central hub for collaboration and backup. Once your local changes are ready, pushing them to GitHub ensures they are safely stored in a remote repository. This also makes it easy for others to review your work, contribute to the project, or collaborate effectively through pull requests and issue tracking.

Although GitHub’s browser interface is useful for quick edits or reviewing code, it lacks the robust capabilities of local development environments. Features like running tests, debugging code, or using integrated development tools are not possible directly in the browser. Additionally, frequent uploads and edits through the browser can be time-consuming and error-prone compared to managing everything locally before syncing with GitHub.

### Useful Git commands

For now, we will only pick up a few basic commands to get started with things. As the course progresses, we will go into the details of what these commands do in the background.

#### 1. `git status`

Having cloned a repository to local and navigated to that repository, `git status` shows you the current state of your project. It tells you which files have been changed, which are ready to be saved (staged), and which still need to be added. It’s a useful command to keep track of what’s going on before you make any further changes. For example, after cloning a repository, we navigate towards it using `cd` (change directory) and then we check the status

```bash
cd <your-repo-name>
git status
```

or add `-v` for a more verbose status

```bash
cd <your-repo-name>
git status -v
```

Assuming we have made not edits to any of the cloned files, then this command will return 

```bash
no changes added to commit (use "git add" and/or "git commit -a")
```

Once you start editting or adding new files to the directory, changed files can conveniently be listed using `git status`, for example:

```bash
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   quick-guide-to-git.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	quick-guide-to-github.md

nothing added to commit but untracked files present (use "git add" to track)
```

Here, Git is telling us that we have some untracked files - quick-guide-to-github.md - present in our working directory which we have not staged nor committed to our local repository yet. Also, it is showing some modifications on the quick-guide-to-git.md file but not staged for commit yet. It is a good practice to always run `git status`, especially when in doubt because it provides helpful information on your current situation. In the example above, `git status` give information on in which branch you are now (On branch main), some untracked files (in this case only one file, but can be multiple files), and a hint if you want to track the files (use `git add` ...). If your current local branch is linked to a remote branch, then `git status` will tell you if your local branch is behind or ahead by any commits.

#### 2. `git add`

`git add` prepares changes you’ve made (like editing files or adding new ones) to be saved. It moves the changes into a "staging area" before they are fully saved. You use this to tell Git which changes you want to include in the next snapshot of the project. For example, in we create a new file named `empty_file.txt`, then we can use:

```bash
git add empty_file.txt
```

This will tell Git that this file should be staged and included in the next commit. If you have made updates to multiple files but only want to save progress on one of them, you can stage just that file with `git add <your-file>`.

#### 3. `git commit`

`git commit` saves the changes that were staged with git add into the project's history. It creates a permanent record of these changes identifiable with a unique ID. Each commit has a message (written by you) to describe what was changed, making it easy to track progress over time. For instance, having created `empty_file.txt` and added it to the staging area, we now commit it to keep a record of the current version.

```bash
git commit -m "added empty_file.txt to be tracked by this repository"
```

the `-m` allows us to add the commit message directly. Each commit requires a message that describes what was changed, providing context for yourself and others about the purpose of those updates. When creating a commit message, it is best to follow clear and concise practices. A good commit message should describe the purpose of the changes and provide enough detail for others (or your future self) to understand the reason behind them. Keep the message short but informative. For example, instead of writing “Fixed a bug”, a better message would be "Fix crash when submitting empty form”. If the commit involves multiple changes, consider breaking them into separate commits so that each one addresses a single logical change. This ensures clarity and makes it easier to review or revert specific updates later.

The key difference between adding and committing is that `git add` prepares changes by staging them, while `git commit` permanently records those staged changes in the repository's history. Without `git add`, no `git commit` would ever do anything. This two-step process gives you control over what gets saved and allows for clear organization of your project's progress.

#### 4. `git push`

Once you have created or modified a file, added and committed it to the repository, you need to push your local update to the remote repository. `git push` sends the commits you’ve made on your local computer to a remote repository (Gitlab, GitHub etc.) so others can see or collaborate on your work. Think of it as uploading your changes to the cloud, where the whole team can access the latest version. If you run `git status` again, it will return:

```bash
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

Git is telling us that our local branch is ahead of the repository branch by two commits. Now, we can push it to the remote server using

```bash
git push origin <branch>
```

If you were exclusively on local (your own computer) and don't make changes remote, then a git workflow will mostly consist of a sequence of `git add`, `git commit` and `git push`. If you work with others or work on multiple devices, then you might want to check if changes have been made to the remote repository that were not included during the original cloning of this remote repository to local. If the `git status` tells that your local branch is **behind** your remote repository, you need to do `git pull` first before `git push` to avoid conflict.

#### 5. `git fetch`

`git fetch` downloads new changes from the remote repository but does not update your local project automatically. It just brings the latest changes into view, letting you inspect them first. You can decide whether to merge them into your local version later. If we want to check whether changes have been made remotely we can use 

```bash
git fetch
git status
```

#### 6. `git pull`

`git pull` downloads the latest changes from the remote repository and updates your local project with those changes. It ensures your version of the project stays up to date with the rest of the team’s work. It combines two steps: fetching changes and merging them.

```bash
git pull
```

Sometimes a file will have changed both remotely and locally. This can create conflicts when pulling remote into local. Resolving these merge conflicts will be a topic for another day.
