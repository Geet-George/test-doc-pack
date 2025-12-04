# Important Differences

## 1. Git v/s Github

Git and GitHub are two different things, but they are often confused with each other. Git is a version control system that lets you manage and keep track of your source code history. GitHub is a cloud-based hosting service that lets you manage Git-based repositories. If you have projects that use Git, then GitHub is designed to help you better manage them.

Very simply put, Git is a tool that you install locally on your computer, while GitHub is a web-based platform that you use to manage your Git repositories. Git is the tool, and GitHub is a service for projects that use Git. There are other services like GitLab and Bitbucket that provide similar services to use and manage Git repositories. You can collaborate with others on such services, and it makes it easy to handle open-source projects.

You can use Git without GitHub, but you cannot use GitHub without Git. It can be a bit confusing at first, but once you start using them, you will understand the difference.

## 2. .py (Python) v/s .ipynb (Jupyter notebook)

Python files have the extension `.py`, and Jupyter Notebook files have the extension `.ipynb`. Python files are used to write Python code, and Jupyter Notebook files are used to write Python code in a more interactive way. Jupyter Notebooks are great for data analysis, visualization, and machine learning projects. You can write code in cells and run them individually, which makes it easier to debug and test your code. You can also write markdown text in Jupyter Notebooks, which makes it easier to document your code and explain your thought process. 

One would wonder if Jupiter Notebooks are so great, why not use them all the time? The answer is that Jupyter Notebooks are great for data analysis and visualization, but they are not great for writing production code. Python files are better suited for writing production code because they are easier to manage and maintain. You can write functions and classes in Python files, which makes it easier to reuse your code. 

The choice between using Python files and Jupyter Notebooks depends on the project you are working on. If you are working on something very quick and dirty (such as immediate data analysis), then Jupyter Notebooks are great. If you are working on something that requires a lot of code and needs to be reused again and again, then Python files are better. In fact, with Python files, you can write your code in a modular way, which makes it easier to test and package your code.

I found [this article](https://learnpython.com/blog/python-scripts-vs-jupyter-notebooks/) that nicely explains the differences between Python files and Jupyter Notebooks in more detail. 

## 3. Local v/s Remote

Local and remote are two terms that are often used in the context of Git and GitHub. Local refers to your local computer, where you have your files and folders stored. Remote refers to a server that is hosted on the internet, where you can store your files and folders. When you work on a project, you make changes to your files and folders on your local computer. Once you are done with your changes, you can push your changes to a remote server, such as GitHub. This way, you can collaborate with others on your project and keep track of your changes.

The sync between your local and remote repositories is not autoamtic, but via Git commands. You can use commands like `git push` to push your changes to a remote repository, and `git pull` to pull changes from a remote repository. You can also use commands like `git clone` to clone a remote repository to your local computer, and `git fetch` to fetch changes from a remote repository. The page on a [quick guide to git](quick-guide-to-git.md) provides more details on how to use Git commands.

## 4. Terminal v/s Editor

The terminal and the editor are two tools that you will use frequently when working with code. The terminal is a command-line interface that lets you interact with your computer using text commands. You can use the terminal to run Python scripts and install packages. The terminal might look boring and dull (and intimidating) at first, but it is a powerful tool that lets you do a lot of things. For Windows users, the terminal is called the Command Prompt, and for Mac users, it is called the Terminal. To open the terminal at a given folder, 

- On Windows, go to your repo folder and you can press `Ctrl + Right-click` and select `Open Terminal here`.
- On Mac, go to your repo folder and you will see the Path Bar shown at the bottom of the Finder window. Right-click on the last folder in your Path Bar (i.e. repo folder) and select `New Terminal at Folder`. If you don't see the Path Bar, you can enable it by going to `View` -> `Show Path Bar`.

The editor is a text editor that lets you write and edit your Python code. You can use the editor to write Python scripts and debug your code. Some editors like VS Code, Spyder, and PyCharm come with features like syntax highlighting, code completion, debugging tools and will even let you run the code. While the editor is a user-friendly tool that makes it easy to write and edit your code, it is not as powerful as the terminal. You can use the editor to write your code, but you will need to use the terminal to run your code and execute all git commands.
