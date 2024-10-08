# Course Overview

```{note}
For help with understanding [Files and Folders](https://teachbooks.github.io/files-and-folders/), there is a nice pilot module developed by the Data Literacy Project at TU Delft. It is a short, self-paced and independent learning course. You can find it [here](https://teachbooks.github.io/files-and-folders/). It is short with some exercises and quizzes to help you understand the basics of files and folders. And although not all aspects of the module might be relevant to this course, I highly recommend you to go through it.
```

Most of you have completed a course introducing programming and Python in Q2 of your first year and this will be the second course where you are taught computer programming. Therefore, this course will not be an introductory one (which it was last year), but an intermediate one. Here, beyond coding in Python you will also learn how to make your code usable for others. You will apply standard software practices to your code and develop your project similar to how things are expected to be done in the software world. This might sound like a lot to learn, but it boils down to 4 simple concepts:

#### (a) Testing 

Sometimes, in changing stuff in our code, we might unknowingly break it. However, we can put tests in place to ensure that no such things happen. It just makes sense to test your code and make sure it is doing what you really want it do. It is as simple as writing out new functions and letting libraries like `pytest` do the job for you. 

#### (b) Documentation 

It helps a great deal to just write down what your code does, how it runs and how a user is supposed to start working it. You'll find that most good software (e.g. Python libraries like [`numpy`](https://numpy.org/doc/stable/user/absolute_beginners.html)) have very good documentation that helps users have an easy start. That might look intimidating, but it starts very simply with writing double quotes (`"`) 6 times. We'll talk about this later.

#### (c) Version control

That's the general name, but it essentially means that you keep track of the changes that your code goes through during its development. For this, you will use a very simple, but amazingly powerful tool called `git`. It helps you keep track of your code, collaborate with others and also helps you go back in time to see what your code looked like before.

#### (d) Packaging

This part is like putting the cake in a box. You have a nice cake (your code), but you want to give it to someone else. You can't just give them the cake on a plate. You need to put it in a box, wrap it up and give it to them. This is what packaging is about, but in this case, people everywhere can enjoy your cake and instead of running out of cake, you get more of it! :)

## Learning Objectives

Upon the successful completion of this course, you will be able to develop a minimal, working Python software package. For developing the Python package, you will learn how to:

1.	Create functions and workflows – these functions will execute tasks of numerical modelling and data analyses
2.	Incorporate testing (unit tests) and documentation (including for API) in your software
3.	Integrate version control (git) and features of reproducibility in your coding practice
4.	Package your software for execution in different machine environments

## Projects

So, what are we going to do with these software concepts? You will have projects of your own to implement them on and by the end of the course, you will have a functioning Python package! On the way, we will also learn about some practicalities like managing environments, about hosting documentation, about collaborating with Gitlab and so on. You will find more details about projects [here](projects/projects.md). 
