# Projects 

Each student designs their own project. You "propose" the project. The teaching staff will go through these projects and will give feedback on the feasibility and suggest any modifications. You can look at [some project themes here](themes.md) to get ideas for the types of projects you can do, but don't feel restricted to them.

The primary objective of your project is to be able to use version control and package the source code with standard practices in software of testing and documentation. The subject matter of the code is secondary (but not unimportant!). Put simply, the code itself should be functioning, even if the content is not perfect. 

For example, if your project aims to predict the weather using a simple linear regression model on temperature, pressure, humidity and winds, you should be able to provide source code that can be run by anyone, and the source code should be well-documented and tested. How well the model can actually predict the weather becomes secondary.

For your project, you will be working on your own project in Gitlab (hosted by TU Delft). This project is part of your submission of your proposed project. Details on how to do this are provided below.

## Project requirements / guidelines

The bigger idea behind the course is to learn how to implement programming concepts to a software project. For the timeframe that we have, it is important to keep the project simple and focused. Here are some guidelines to help you design your project:

1. **Name and student number**: Add your name and student number in the README of your project, immediately after the title.

2. **Python and libraries**: The project should be written in Python. You can use any version of Python, but it is recommended to use Python 3.6 or higher. Please do not use niche libraries that are not commonly used. If you are unsure, ask the teaching staff. 

2. **Feasibility**: The project should be feasible to complete within the time frame of the course. This is why the project should not take on tasks which require any of the following:

    a. Creating new data for the project

    b. Implementing advanced functions by yourself because they are not available with standard libraries such as with scipy

    c. Developing deep-learning models. While it is a good idea to learn such aspects, it does not fit well with the scope of this course. 

3. **Scope**: Relating to the point on feasibility is the scope of the project. The project must not undertake tasks that are too large in scope. Better to err on the side of a smaller project than a larger one. If you want to do a larger project, I encourage you to do it after the course. For an example with data visualization, I would recommend against implementing a complex graphical user interface instead of starting with simply generating and saving plots.

4. **Robustness**: Do not propose a project where it is unclear if the method would work, for example, if it is not a standard method and hasn't been tested before. This project is not a research project, but simply a testbed for the different programming concepts we will learn. For example, you want to work on a project that recommends private v/s public transport based on some user inputs. But if there doesn't exist a method to determine the best mode of transportation for a given user, you must not spend your time developing this method and you must choose a different project instead.

5. **Subjective projects**: Projects that have a subjective or qualitative core to them should be avoided. For example, a project which provides tourist recommendations for a given city, or a project that recommends a book based on a user's preferences. Such projects are difficult to test and evaluate. 

6. **Data**: If your project requires data, you should be able to provide the data or have access to it. If you are unsure about the data, please ask the teaching staff. You might be asked to change or modify the project if the relevant data is not available at hand. We do not encourage any creation of data (randomizers for testing or proof of concept is okay), or getting resources to access data that is not freely available.

7. **Too flexible**: If your project tries to implement too many methods or if it provides too many choices, this might make it more difficult to finish in time as well as to keep all the moving parts running. You may try more flexibility in your project after the course. For the course, please keep it minimal. 

## Feedback and Support

The teaching team will provide feedback on your project proposal. This feedback will be given in the form of issues on your Github repository titled something like “Proposal Feedback”. You are expected to address these issues and make the necessary changes to your project proposal. 

Further communication about your project should also continue over the Github repository. If you have any questions or need help, you can create an issue on your repository. You'll find the instructions on [raising an issue here](../../learning/guide-to-raising-issues.md). Follow the template provided there and tag the instructor and TAs.

## Proposal Requirements and Deadline

**The deadline for submitting your proposal is 19th September, 10:00 CEST.**

In [Gitlab hosted by TU Delft](https://gitlab.tudelft.nl/) you should be able to login with your NetID. Create a new (blank) project on Gitlab. Give it an appropriate name. This name should reflect what your code does or what your project is about, not with your name or words such as `assignment` or `proposal` in the name. [Points 1-6 in this article](https://sd.blackball.lv/en/articles/read/18956) will help you with naming. For your project, you can set any visibility level, however if you choose "Private", you must add the instructor and all TAs as members in the project. Initialize the repository with a README, and in this `README.md`, you will write down 

i. a brief description of the project

ii. the algorithm / library / methods that you want to use

iii. any data that you might need

iv. the expected outcome 

The whole description should not be more than 400 words.

To complete the aforementioned tasks, you will need to first understand a few small things about `git`. Think of this as a small exercise to build up your git basics, which you will find very useful in the course and much much beyond. You'll find a [quick guide to using git here](../../learning/quick-guide-to-git.md), including cloning your repository from Gitlab to your computer locally and then committing your changes.

Commit the additions in the `README` to your project, after which the teaching team will be able to view it and provide you with feedback. 
