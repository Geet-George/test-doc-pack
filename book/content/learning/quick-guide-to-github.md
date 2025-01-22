# 3.2. GitHub - A Quick Introduction

A GitHub repository is a storage space where you can organize, share, and collaborate on your project files. It includes:
- Code and Files: your project's files and their revision history.
- README: a file providing an overview of the project.
- Branches: separate versions of your project for development or experimentation.
- Commits: snapshots of changes made to the files over time.

## Setting up a repository on GitHub

To create a new repository, you need to log in to your GitHub account. In the upper-right corner, click the `+` icon an select `New repository`. Then, fill in some details as follows:
- `Repository Name`: choose a short, descriptive, and memorable name for your repository (e.g., detrend-timelines). Avoid special characters and spaces; use hyphens or underscores instead.
- `Description` (optional): add a brief explanation of your project.
- `Visibility`: choose between `Public` (visible to everyone) or `Private` (restricted access).

It is a good practice to initialize your new repository with a `README` file to provide basic information about your project. Optionally, you can add a license to your new repository. More explanation about licensing can be found [here](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository).

Finally, click `Create repository` to finalize your new repository.

## Cloning an existing GitHub repository

Cloning an existing GitHub repository is required when you want to work locally on that project. First, navigate to the repository that you want to clone on GitHub. Click the green `Code`button and copy the URL (SSH or HTTPS). Then, open your terminal (MacOS/Linux users) or command prompt (Windows users), navigate to the directory where you want to have the local copy of the repository, and run the following command:

`````{tab-set}
````{tab-item} SSH
 
```bash
git clone git@github.com:<your-Github-user-name>/<your-repository-name>.git
```

````

````{tab-item} HTTPS

```bash
git clone https://github.com/<your-Github-user-name>/<your-repository-name>.git
```

````
`````

This clones the Github directory `<your-repository-name>` in whatever folder you use this command. For example, if you opened the terminal or command prompt in your Documents folder, it will create a new folder with `<your-repository-name>` there and copy the contents of the repository into that folder.

With the HTTPS option, you will have to log in and provide credentials for each communication with the remote server. Meanwhile, you only need to do an authentication once with the SSH option after setting up the SSH key. GitHub provides full documentation and guides on how to [generate an SSH key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent), but a short summary of the commands you need to perform is shown below.

To generate an SSH key pair, you will need to run the ssh-keygen command from your command line tool/GitBash as shown below.

```bash
ssh-keygen -t ed25519 -C "your-email@example.com"
```

Next, you need to copy your public key (the file should have the extension “.pub”) over to your GitHub account. The `ssh-keygen` command above will let you know where your public key is saved, and you can get its contents as follows:

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

## Initializing a local directory as a Git repository

If you already have a directory containing all files on your project, you can initialize a new repository from your local machine. Open your terminal (MacOS/Linux users) or command prompt (Windows users), navigate to the directory where you have your project, enter that directory, and run the following command:

```bash
git init
```

This transforms the current directory into a Git repository, such as GitHub. Once you have initialized the repository, you need to create a remote repository on GitHub (do not initialize with `README`). Then, add the remote URL to your local git repository with 

```bash
git remote add origin <URL>
```

This stores the remote URL under a more human-friendly name, `origin`. Shape your history into at least one commit by using

```bash
git add .
```

This stages the existing files for commit. Then, make the snapshot of staged changes with a message using

```bash
git commit -m "initial commit"
```

Once you have at least one commit, you can push to the remote by doing

```bash
git push -u origin main
```


## `git init` vs `git clone`

To start a repository, use either `git init` or `git clone` - not both. If the repository already exists on a remote, you would choose to `git clone` and not `git init`. On the other hand, your project may already exist locally, but it doesn't have Git yet. In this case, `git init` is probably the right choice for you. You ony need to run `git init` once to initialize the repository.
