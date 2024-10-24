# Packaging

So, what’s the deal with packaging our project? We already have our code in a folder—can’t we just zip it up and send it to someone?

Sure, you can do that! But packaging goes beyond simply zipping up your code. It’s about making your code easy to install and use for others. When you package your code, you create a distributable version that can be installed on other machines. Now, what’s this new term: ***distributable***?

A distributable is a version of your code that’s ready for others to use. Think of it like a cake that only needs to be taken out of the box and served—no baking or frosting required. In this analogy, the baking and frosting represent the installation and setup that a user would have to handle if you just sent them a zipped folder. By packaging your code, you make it so that the user only needs to run a few simple commands, like pip install your-package.

## The `pyproject.toml` file

When you package your code, you create a distributable version known as a package. A package is a collection of Python files that can be easily installed using a package manager like `pip`. `pip` is the Python package manager that helps you install and manage Python packages.

So, how does `pip` know what to do with your package? How does it know what to install and where? That’s where the `pyproject.toml` file comes in. The `pyproject.toml` is a file, which provides `pip` with all the necessary information about your project, such as your package name, version, dependencies, as well as instructions on how to build it. With this file, you ensure that your package is straightforward to install and use!

What does the `pyproject.toml` file look like? Here’s an example:

```toml
[build-system]
requires = ["setuptools"]
build-backend = "setuptools.build_meta"
```

Create a new file in your project's root directory and name it `pyproject.toml` (do not change the name of the file, keep it exactly `pyproject.toml`). Copy the above content into the file and save it.

This is the most basic `pyproject.toml` file that you can have. It tells `pip` that your project uses `setuptools` as the build system. `setuptools` is a package that helps you build and distribute Python packages. The `build-backend` key specifies the build backend that `setuptools` should use to build your package. In this case, it’s `setuptools.build_meta`. But that is not something you need to worry about right now. Just know that this is the minimum you need to have in your `pyproject.toml` file and that `setuptools` is a popular example of a build system, not the only one.

## Adding metadata to your package

The `pyproject.toml` file is not just for specifying the build system. It can also contain metadata about your package. Metadata is information about your package, such as its name, description, version, and author. This information helps users understand what your package does and how it can be used.

Here’s an example of how you can add metadata to your `pyproject.toml` file:

```toml
[build-system]
requires = ["setuptools"]
build-backend = "setuptools.build_meta"

[project]
name = "my-package"
description = "A simple package that does something cool"
authors = [ 
    {name = "Your Name", email = "you@yourdomain.com"},
]
```

In this example, we’ve added a new section called `[project]` to the `pyproject.toml` file. This section contains metadata about your package, such as its name, description, and authors. 
