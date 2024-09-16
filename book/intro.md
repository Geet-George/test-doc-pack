(intro)=
# AESB2122 - Introduction

Welcome to the Python part of AESB2122 Signals and Systems with Python! 

Here you'll find the learning material for the Python-relevant part of the course. I hope you can use this book (set of webpages) as a source to keep coming back to for references on learning and understanding programming concepts that you will apply for your project in this course. You've already had a course on Python programming in your first year. This course will focus on concepts to make your Python code more in line with what is standard practice in the software world.

But why learn these concepts in the first place? Are we not training to be applied earth scientists and engineers? Why learn software programming and development concepts? 

*Short answer:* because it's fun (after a while)!

*Longer, maybe more convincing, answer:* because you will be able to automate tasks that you would otherwise do manually, you will be able to share your work with others without hassle and you will be able to make your work reproducible. Such skills will not only be useful in your academic work, but also in your professional life, independent of the field you choose to work in. 

Let's now look at the broader picture of software development and then see how our course fits into this picture.

## Software Development

The simplest software development is just "code and fix". Most of us start with this. We write some code, run it, see what's wrong, fix it and repeat. This is fine for small scripts, but as the code grows, this becomes a nightmare. We might forget what we did, we might break something that was working before and we might not be able to share our work with others.

This is where better software practices come in. In essence, it is still the "code-run-fix" cycle, but with more sophistication so as to make the process more efficient, less error-prone and just make life easier.

Software projects (like other projects) have a lifecycle. This lifecycle is usually divided into the following stages:

1. **Planning**: What do you want to do? What are the requirements? What are the constraints? What are the risks?

2. **Design**: How will you do it? What are the components? How do they interact?

3. **Implementation**: Write the code!

4. **Testing**: Does the code do what it is supposed to do? Does it handle errors well?

5. **Documentation**: How do you use the code? How does it work? How do you contribute to it

6. **Deployment**: How do you share the code with others? How do you make it easy for others to use it?

7. **Maintenance**: How do you keep the code up-to-date? How do you fix bugs? How do you add new features?

These stages could be linear (such as in the [Waterfall model](https://en.wikipedia.org/wiki/Waterfall_model)) or iterative (such as in the [Agile model](https://en.wikipedia.org/wiki/Agile_software_development)). The choice of model depends on the project and the team working on it. In practice, most projects use a mix of these models. 

## Our Course

In this course, we will focus on the **Implementation**, **Testing**, **Documentation** and **Deployment** stages, although we will touch upon the other stages as well. For example, your [project proposal](content/course/projects/projects.md) includes the **Planning** and **Design** stages. 

We will use Python as the programming language for this course. We will also rely on Git for version control and Gitlab for collaboration. We will use libraries such as `pytest` for testing and `sphinx` for documentation. We will also learn about packaging our code with [PyPi](https://pypi.org/) so that it can be shared with others. At the end of the course, you will have a functioning Python package that you can simply:

```bash
pip install your-package-name
```

More course details are available in the [course overview](content/course/overview.md).

## Feedback welcome 

This being a digital "textbook", we hope to continue improving the content here and provide you with the best form of resources for your learning. If you have any feedback, please feel free to email me at g.george@tudelft.nl or better yet, [raise an issue in the Github repository](https://github.com/Geet-George/test-doc-pack/issues/new).