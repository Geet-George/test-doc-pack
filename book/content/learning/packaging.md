# Packaging

So, what’s the deal with packaging our project? We already have our code in a folder—can’t we just zip it up and send it to someone?

Sure, you can do that! But packaging goes beyond simply zipping up your code. It’s about making your code easy to install and use for others. When you package your code, you create a distributable version that can be installed on other machines. Now, what’s this new term: ***distributable***?

A distributable is a version of your code that’s ready for others to use. Think of it like a cake that only needs to be taken out of the box and served—no baking or frosting required. In this analogy, the baking and frosting represent the installation and setup that a user would have to handle if you just sent them a zipped folder. By packaging your code, you make it so that the user only needs to run a few simple commands, like pip install your-package.

## The `pyproject.toml` file

When you package your code, you create a distributable version known as a package. A package is a collection of Python files that can be easily installed using a package manager like `pip`. `pip` is the Python package manager that helps you install and manage Python packages.

So, how does `pip` know what to do with your package? How does it know what to install and where? That’s where the `pyproject.toml` file comes in. The `pyproject.toml` is a file, which provides `pip` with all the necessary information about your project, such as your package name, version, dependencies, as well as instructions on how to build it. With this file, you ensure that your package is straightforward to install and use!