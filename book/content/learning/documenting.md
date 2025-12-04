# Documenting your work

Documenting your work is an essential part of the software development process. It helps others, but more importantly, it helps you. A few months after you've written a piece of code, you might not remember what it does or why you wrote it in a certain way. If you've documented it well, you can easily understand what you did and why you did it. There are several ways to document your work, such as writing docstrings for your functions, and writing a `README.md` file in your repository. We'll learn these in our course. 

You can of course also make your documentation very elaborate with more formal documentation tools like Sphinx. It is also good to document the changes you make to your code, so you can easily track what you've done. This is done by writing detailed commit messages. Such messages should explain why you have made the changes you made; documenting what you have changed usually is redundant because one can already look through the codebase that the commit changes and figure that out. But why you made the changes is not always clear from the code itself.

## Simple README documentation

The most basic form of documentation is the `README.md` file in your repository. This file ideally contains the following information:

1. A title for your project
2. A short description of your project
3. How to run your project

If relevant to your project, you can also include other information, such as:

- How to install your project
- How to contribute to your project
- How to report bugs

But the latter points are more relevant for larger projects that are meant to be used by others. For your projects in this course, the first three points are the most important. Let's take an example. Suppose you have a project that calculates the distance between two cities. Your `README.md` file could look like this:

````markdown
# City distance calculator

This project calculates the distance between two cities.

## How to run

```bash
python main.py
```
````

The above example, although suffices our conditions, is a bit too simple. It would be better to include a bit more information, such as how the project works, and what the user can expect. Here is a more elaborate example:

````markdown
# City distance calculator

This project calculates the distance between two cities. It uses the Haversine formula to calculate the distance between two points on the Earth. The user can input the names of two cities, and the program will output the distance between them.

## How to run

```bash
python main.py
```

The program will then ask you to input the names of two cities. It will then output the distance between them.
````

This is a bit more informative, and it gives the user a better idea of what the project does. But you can add more information that is specific to how your project runs, e.g. what are the dependencies (such as Python should be installed), what is the format that the user should input the data in, what are the units of the output, etc. Of course, for your project, other details might be more relevant.

````markdown
# City distance calculator

This project calculates the distance between two cities. It uses the Haversine formula to calculate the distance between two points on the Earth. The user can input the names of two cities, and the program will output the distance between them.

## How to run

To run the project, you need to have Python installed. Then you can run the following command:

```bash
python main.py
```

The program will then ask you to input the names of two cities. The names should be entered in the following format: `City1, Country1; City2, Country2`. For example, `Amsterdam, Netherlands; Paris, France`. The program will then output the distance between the pairs of cities in kilometers.
````

## Docstrings

Docstrings are a way to document your functions in Python. They are written as strings, and they are placed at the beginning of a function. They should describe what the function does, what the input parameters are, and what the output is. Here is an example:

```python
def my_add_function(a, b):
    """
    This function adds two numbers.

    Parameters:
        a (int): The first number
        b (int): The second number

    Returns:
        int: The sum of the two numbers
    """
    return a + b
```

Let's break down the docstring:

- The first part is a short description of what the function does.
- The next part describe the parameters that the function takes. In this case, the function takes two parameters, `a` and `b`, which are both integers, indicated by `int` in parantheses.
- The last part describes what the function returns. In this case, it returns an integer.

There are various standard conventions for writing docstrings, and you can find them in the [PEP 257](https://www.python.org/dev/peps/pep-0257/). But the style I showed here is a good starting point, i.e. a short description, followed by a description of the parameters and the return value. You can also include examples of how the function runs in your docstrings.

Docstrings are thus very useful because they help you remember what your functions do, and they help others understand your code. For example, if someone else needs to use your function, they can read the docstring to understand how to use it. They could either go visit the function or simply type `help(my_add_function)` in the Python interpreter to see the docstring. 

```{note}
Try it out in your project! Add docstrings to your functions, and call `help(your_function_name)` on them to see the docstrings. This is also how you get help on the arguments and outputs of built-in functions in Python or when you are using functions in popular libraries like numpy. Try running `help(print)` or `help(np.sum)` and see what you get. 
```

These docstring are also used by tools like Sphinx to generate documentation for your code. For example, [the reference for the `np.fft.fft` function of numpy](https://numpy.org/doc/stable/reference/generated/numpy.fft.fft.html#numpy.fft.fft) is generated automatically from the docstring of the function. It is not manually typed out. So, every time there is a change in the function, the documentation is updated automatically.

Therefore, consider docstrings as a way to document your code, and not just as a way to write comments. They are more formal and structured than comments, and they are more useful for others to understand your code. And trust me, in some time, you will also be the "other" who will need to understand your code.