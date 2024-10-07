# Python in a Terminal

You probably started learning Python with Jupyter notebooks and are now comfortable with it — writing code, running cells, and seeing instant feedback. But Python isn't just limited to notebooks! You can run Python directly from your computer's terminal (also called the command line or shell). This is super useful for running standalone Python scripts or automating tasks without needing a notebook. Let’s get you started on running Python in the terminal!

## Why Should You Care About the Terminal?

One might ask why use Pyton in a terminal, when we can already use Jupyter notebooks (also, the terminal looks so boring compared to a notebook), but here’s why learning to use Python in the terminal is worth it:
1. **Run scripts faster**: No need to open Jupyter every time—just execute the file in seconds.
2. **Automate tasks**: Python is great for scripts that you can set up to run at certain times or in certain conditions.
3. **Learning to use the terminal is a superpower**: It gives you more control over your computer and helps in understanding how systems work.

Now, let’s walk through the steps to get Python running in your terminal.

---

## 1. Opening the Terminal

First things first, let’s open the terminal on your computer. 

`````{tab-set}
````{tab-item} Windows

For Windows users, the easiest way to get started is with Anaconda Prompt. From Anaconda Navigator, open Anaconda Prompt, which we will use as your terminal. 

````
````{tab-item} MacOS / Linux
For Mac or Linux users, you can open Terminal by pressing `Cmd + Space` and typing **Terminal**. 

Note: If you aren’t seeing `(base)` in your Terminal, you need to either initialize conda or activate your base environment. To do those, follow the steps below:

To initialize conda, type:
```bash
conda init
```

To activate your base environment, type:
```bash
conda activate base
```

````
`````

If any of the above steps don't work for your machine, approach the teaching team for help.

---

## 2. Check if Python is Installed
Before running Python, we need to make sure it’s installed.

### Type this command in the terminal:
```bash
python --version
```

- If Python is installed, you’ll see something like:
  ```
  Python 3.x.x
  ```
  Yay! You’re ready to go.

- If you get an error like "command not found", Python isn’t installed or isn’t added to your system’s PATH. Don’t panic! Download and install it from the [official Python website](https://www.python.org/downloads/), and make sure to check the box that says **"Add Python to PATH"** during installation (important for Windows users). If it still doesn’t work, approach the teaching team for help.

---

## 3. Running Python in Interactive Mode
Now that Python is set up, let's run it in **interactive mode**, where you can type Python commands and see the result immediately—just like in a notebook!

### Type this in your terminal:
```bash
python
```

You should see something like this:
```
Python 3.x.x (some more text...)
>>>
```
Now you can type Python code directly! Try typing this to make sure it works (press the Enter / Return key after typing the line):
```python
print("Hello from the terminal!")
```

To exit interactive mode, simply type:
```bash
exit()
```

That’s it! You’ve just run Python in the terminal. 🚀

But wait, what if you want to write down a longer script and run it all at once? You can do that too! Let’s move on to the next step.

---

## 4. Running Python Files from the Terminal

To get the full power of Python in the temrinal, you’ll want to run Python files directly. This is where you can write longer scripts and run them all at once. Let’s level up and run a simple, Python file from the terminal.

### Create a Python File in Jupyter

Since you’ve been working in Jupyter, let’s use it to create a `.py` file instead of using external text editors.

- **In your Jupyter Notebook interface**:  
    - Click on **File** > **New** > **Text File**.  
    - Name the file **`hello.py`**.  
    - Inside the file, write the following code:
    
    ```python
    print("Hello from a Python file!")
    ```

    - Save the file.

If you're not using Jupyter, but an external text editor or a different IDE (like VS Code or PyCharm), create a new file named **`hello.py`** and write the same code in it.

### Navigate to the Folder in the Terminal
Now, in your terminal, navigate to the folder where your file is saved. You can navigate to it using `cd path/to/hello.py`. You can copy the file path from your file explorer and paste it after `cd` to directly navigate to the folder. 

`````{tab-set}
````{tab-item} Windows

On Windows, open the folder where your file is saved. You'll see the path in the address bar. Right-click on it and select **Copy address as text**. 

Then, in the terminal, type:

```bash
cd <paste the path here>
```

Note that if you have spaces in your folder names, you can use quotes around the path. For example:
```bash
cd "C:/Users/Your Name/Desktop/folder name"
```

````
````{tab-item} MacOS

On Mac, open the folder where your file is saved. You'll see the path in the Finder window. Right-click on the last folder in the path bar and select **Copy "folder name" as Pathname**.

Then, in the terminal, type:

```bash
cd <paste the path here>
```

Note that if you have spaces in your folder names, you can use quotes around the path. For example:
```bash
cd "Users/Your Name/Desktop/folder name"
```

````
`````


### Run the Python File
Now, you’re in the folder where your Python file is saved. To check if the file is there, type:
`````{tab-set}
````{tab-item} Windows
    
```bash
dir
```
````

````{tab-item} MacOS / Linux

```bash
ls
```
````
`````



To run the Python file, type:
```bash
python hello.py
```

You should see the output:
```
Hello from a Python file!
```

Boom! You've just run your first Python file from the terminal. 🎉

----

Now you know how to run Python in the terminal! It might feel different from the interactive notebook world, but it's an important skill for any Python programmer. Plus, once you get the hang of it, you’ll find it’s a fast and powerful way to work with Python.

Happy coding, and see you in the terminal! 💻⚡
