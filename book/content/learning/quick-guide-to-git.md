# Git - A Quick Guide

This is supposed to be a quick reference guide to using Git. It is not meant to be comprehensive. For a good understanding of Git, I would highly recommend the freely available [Pro Git book](https://git-scm.com/book/en/v2). The book is an excellent resource not just for beginners, but also for advanced users who can use it as a reference to understand what goes on under the hood.

### What does Git do and why use it?

Very simply put, Git keeps track of changes in your code. Well, it actually [takes snapshots](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F) of your code at every change. 

Why is that useful? Think of it this way: you have a project that you are working on. You make some changes to the code and it works. You make some more changes and it breaks. You want to go back to the version that worked. You can do this manually by saving different versions of your code in different files, but this can get messy very quickly. Git helps you keep track of these changes and helps you go back to the version that worked. Nice to have a safety net, right?

But Git is not just about **going back in time**. You can also **work on different branches** of the same codebase in parallel. This is very useful when you want to try out new features without breaking the main codebase. You can also **collaborate smoothly with others** and everyone can make their own changes. Git helps you keep track of who did what and when. It also helps you merge your changes with others' changes. 

The more you use it, the more you will come to appreciate its power and simplicity. I've been using Git for over 5 years now and am still amazed every now and then at how much it can do. 

So, let's get Git going on our computer then...

### Get Git to work on your machine

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

### Useful Git commands

For now, we will only pick up a few basic commands to get started with things. As the course progresses, we will go into the details of what these commands do in the background.

#### 1. `git clone`

`git clone` creates a local copy of an existing project stored in a remote Git repository (like Gitlab or Github). Here Local refers to things stored on your computer, and remote refers to some server. `git clone` is the first step when collaborating on an existing project. For example:

```bash
git clone git@github.com:<your-Github-user-name>/<your-repository-name>.git
```

This clones the Github directory `<your-repository-name>` in whatever folder you use this command. For example, if you opened the terminal in your Documents folder, it will create a new folder with `<your-repository-name>` there and copy the contents of the repository into that folder. The above example is only possible with an SSH key which identifies you to the server without having to log in. GitHub provides full documentation and guides on how to [generate an SSH key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent). A short summary of the commands you need to perform is shown below.

To generate an SSH key pair, you will need to run the ssh-keygen command from your command line tool/GitBash as shown below.

```bash
ssh-keygen -t ed25519 -C "your-email@example.com"
```

Next, you need to copy your public key (the file should have the extension “.pub”) over to your Github account. The `ssh-keygen` command above will let you know where your public key is saved, and you can get its contents as follows:

`````{tab-set}
````{tab-item} Windows
Open Command Prompt and run the following command:

```bash
type C:\Users\<YOUR_USERNAME>\.ssh\id_ed25519.pub
```

````

````{tab-item} MacOS / Linux
Open Terminal and run the following command:

```bash
cat /Users/<YOUR_USERNAME>/.ssh/id_ed25519.pub
```

````
`````

Copy the complete line of output that starts with “ssh-ed25519” and ends with your email address. Finally, go to `Github -> Your profile -> Settings -> SSH and GPG Keys -> New SSH key` page to add a new SSH public key. Paste the public key from your clipboard into the box labelled `Key` (making sure it does not contain any line breaks), give your key a name, then click the `Add SSH key` button.

Alternatively, you can clone the Github repository with HTTP:

```bash
git clone https://github.com/<your-Github-user-name>/<your-repository-name>.git
```

But then you will have to log in and provide credentials for each communication with the remote server

#### 2. `git status`

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

Once you start editting or adding new files to the directory, changed files can conveniently be listed using `git status`

#### 3. `git add`

`git add` prepares changes you’ve made (like editing files or adding new ones) to be saved. It moves the changes into a "staging area" before they are fully saved. You use this to tell Git which changes you want to include in the next snapshot of the project. For example, in we create a new file named `empty_file.txt`, then we can use:

```bash
git add empty_file.txt
```

To tell Git that this file should be staged and included in the next commit.

#### 4. `git commit`

`git commit` saves the changes that were staged with git add into the project's history. It creates a permanent record of these changes identifiable with a unique ID. Each commit has a message (written by you) to describe what was changed, making it easy to track progress over time. For instance, having created `empty_file.txt` and added it to the staging area, we now commit it to keep a record of the current version.

```bash
git commit -m "added empty_file.txt to be tracked by this repository"
```

the `-m` allows us to add the commit message directly

#### 5. `git push`

`git push` sends the commits you’ve made on your local computer to a remote repository (Gitlab, GitHub etc.) so others can see or collaborate on your work. Think of it as uploading your changes to the cloud, where the whole team can access the latest version. Now that we have created a new file, added and committed it to the repository, we can push it to the remote server using.

```bash
git push
```

If you were exclusively on local (your own computer) and don't make changes remote, then a git workflow will mostly consist of a sequence of `git add`, `git commit` and `git push`. If you work with others or work on multiple devices, then you might want to check if changes have been made to the remote repository that were not included during the original cloning of this remote repository to local. 

#### 6. `git fetch`

`git fetch` downloads new changes from the remote repository but does not update your local project automatically. It just brings the latest changes into view, letting you inspect them first. You can decide whether to merge them into your local version later. If we want to check whether changes have been made remotely we can use 

```bash
git fetch
git status
```

#### 7. `git pull`

`git pull` downloads the latest changes from the remote repository and updates your local project with those changes. It ensures your version of the project stays up to date with the rest of the team’s work. It combines two steps: fetching changes and merging them.

```bash
git pull
```

Sometimes a file will have changed both remotely and locally. This can create conflicts when pulling remote into local. Resolving these merge conflicts will be a topic for another day.
