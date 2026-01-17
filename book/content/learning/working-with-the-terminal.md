# 0. Working with Terminal
In the next few chapters you'll be passing instructions to your computer without using a Graphical User Interface (GUI). An effective way of directly communicating with your computer is through the Terminal/Powershell/Anaconda Prompt/Git BASH/etcetera . Which you'll be using, depends on your operating system and software of choice (such as Anaconda Prompt, Git BASH). For ease, we'll ignore the semantic differences and refer to everything as the terminal.

Commands on the terminal are slightly different depending on your operating system. Things are mostly streamlined for Unix systems (Linux and MacOS), with some changes to Windows commands. Tools like Git BASH let you use Linux-esque commands on Windows, which is nice! 

## 1. Navigating the Terminal

### 1.1 Where am I?
After opening a terminal you can use it to navigate through the directories on your computer. Which directory you are located in is usually displayed in the terminal prompt. This is often abreviated. To print your full current working directory use:

`````{tab-set}

````{tab-item} Windows
The command `cd` stands for "Change Directory", which is actually not what we want to do here, but if you don't provide arguments it will return your current directory instead. Neat, ey?
```powershell
cd
C:\Users\Username
```
````

````{tab-item} MacOS / Linux
The command `pwd` stands for "Print Working Directory"
```bash
pwd
/Users/username
```
````

`````

### 1.2 Changing Directories
Excellent, now we know are current wprking directory. Often you might have to navigate to a particular file located in another folder. To change your working directory to that folder we can use the Change Directory `cd` command. Submit the directory you want to change to after `cd`.

`````{tab-set}

````{tab-item} Windows
If we are in `C:\Users\Username` and we want to navigate to `C:\Users\Username\documents\scripts`, then we could use
```powershell
cd documents\scripts
```
````

````{tab-item} MacOS / Linux
If we are in `/Users/Username` and we want to navigate to `/Users/Username/documents/scripts`, then we could use
```bash
cd documents/scripts
```
````

`````

To check that the directory change was successful you can print your current working directory as discussed in 1.1. 

There are many tricks and shortcuts when changing directories. Some useful ones are 
- `cd ~` : Returning to the home directory (try it)
- `cd ..`: Going up one directory
- `cd -` : Going back to the previous directory
- When typing out a long directory name or command, press `tab` to autocomplete (definitely try this one!)

### 1.3 What is in my directory?

Depending on which terminal/system you use, a different command might be needed to list all the files and folders in your current directory. On windows `dir` should work, and on Unix `ls` is the standard. Though, on Windows Powershell `ls` is also accepted.

`````{tab-set}

````{tab-item} Windows
```powershell
dir
```
````

````{tab-item} MacOS / Linux
```bash
ls
```
````

`````

Both the Windows and Unix commands take many arguments that may be useful, such as to list also hidden files/folders (names starting with a `.` like `.git`), only folders, only files with a particular extension, etc. etc. The internet is your friend for these.

### 1.4 Miscellaneous

#### ECHO
To print something in the terminal you can use the `echo` command. You'll find this command all over the place. 

#### Python
If you have python installed and added to your path, you can run it by calling `python` directly in the terminal. This works for many programs. In the next chapter we'll discuss running Python files from the terminal
