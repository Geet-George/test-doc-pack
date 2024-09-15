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

## Useful Git commands

### `git status`

### `git clone`

### `git add`

### `git commit`

### `git push`
