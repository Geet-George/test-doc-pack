# Local to Remote (Communicating changes to Github)

In this guide, you'll learn how to add your Python functions to `.py` files (learn how to work with `.py` files [in the Python-in-a-Terminal guide](python-in-a-terminal.md).)and push them to your remote repository on GitHub. We assume you’ve already completed the setup (installed Git, configured user details, cloned your repository) as explained in the [Quick Guide to Git](quick-guide-to-git.md).

---

## Step 1: Create or edit a Python file

1. **Edit your Python file**: Create or edit a `.py` file in your local repository.
   
   - Suppose you add some Python code to the file `functions.py` as follows:
     ```python
     def greet():
         return "Hello, GitHub!"

     print(greet())
     ```
---

## Step 2: Stage your changes

After saving your `.py` file, you need to stage it for a commit. In your terminal:

1. **Navigate to your project directory**:
   ```bash
   cd path/to/your/repository
   ```

2. Check the status of your repository:
```bash
git status
```

You should see your new or modified `functions.py` file listed as an untracked file or modified file.

3. Stage the file for commit
```bash
git add functions.py
```

If you have multiple files to add, you can stage all changes by running:

```bash
git add .
```

---

## Step 3: Commit your changes

Now that your changes are staged, you need to commit them. Committing is like saving a snapshot of your project at a specific moment.

1. Commit your changes with a message:

```bash
git commit -m "add greeting function"
```

Make sure your commit message is meaningful, so it's easy to understand what changes were made.

## Step 4: Push to Github

Once your changes are committed, it's time to push them to your remote repository on GitHub.

```bash
git push origin main
```
This will upload your latest changes to the main branch of your GitHub repository.

## Step 5: Verify your changes on GitHub

After pushing, you can check your GitHub repository to see the changes reflected. Go to your GitHub repository in your browser. Check your repository files and you should see your .py file with the changes you made.

## Step 6: Making future changes

Whenever you make further changes to your Python files or add new ones, follow the same steps:

1. Edit your files.
2. Stage the changes with `git add`.
3. Commit the changes with `git commit`.
4. Push the changes to GitHub with `git push`.






