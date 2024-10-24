# Contributing to test-doc-pack

Firstly, thanks for thinking of contributing to test-doc-pack. You can help out by submitting issues (when you encounter bugs, typos, inconsistent information, etc.) or by adding to the content here. To know how to get started with content development, jump to [Development Workflow](#development-workflow). This book is also compiled with [Jupyterbook](https://jupyterbook.org/en/stable/content/) and helped by the [Teachbooks](https://teachbooks.tudelft.nl/) template. You will find additional resources there to help with development details particular to those environments.

If you want to contribute, but don't know where to start, you can also have a look at the [issues](https://github.com/Geet-George/test-doc-pack/issues) and you will find where test-doc-pack needs help. Pick an issue and assign it to yourself, so others know that you are working on that. If you are not sure how to proceed, you can express your interest by commenting on the issue, and someone should help you out.

## Development Workflow

1. **Fork & clone test-doc-pack**

    Fork the [test-doc-pack](https://github.com/Geet-George/test-doc-pack) repository.

    Clone your fork and set the original repository to remote upstream with the following commands:

    ```bash
    git clone git@github.com:<your-github-username>/test-doc-pack.git
    cd test-doc-pack
    git remote add upstream git@github.com:Geet-George/test-doc-pack.git
    ```

2. **Create a branch**

    Now we have a local copy of our fork and we can start developing.

    It is always good coding practice to work on a different branch every time you start working on a new feature / bug-fix (yes, despite having your own fork).

    Create a branch and checkout to start working on it.
    ```bash
    git branch my-new-feature
    git checkout my-new-feature
    ```
    > Alternatively, do it all in one line.
    > ```bash
    > git checkout -b my-new-feature
    > ```
    > Note that regardless of which branch you are on currently, you can still specify off which branch you want to create a new branch by (shown here as branch off `main`):
    > ```bash
    > git branch my-new-feature main
    > ```

3. **Make your changes**

    Do your edits and push to your fork. Behold git's holy trinity!

    ```bash
    git add . # will add all uncommitted changes
    git commit -m "your commit message here" # consider giving a detailed message & not simply a header
    git push # for the first push of a branch, track it e.g. git push -u origin my-new-feature
    ```

    Every commit makes changes that are justified by one reason. The size of a commit could be a single character change or a change in thousands of lines across millions of files. But the reason behind the commit should ideally be as solitary as possible. Commit often, but not too often. I think Henry VIII might have said that.

    If you'd like to see how the changes you've made in the documentation look, you can build the book locally. You can do this by running the following command in the terminal:

    ```bash
    teachbooks build book/
    ```

    Be sure that you have the `teachbooks` package installed. If not, you can install it by running:

    ```bash
    pip install teachbooks
    ```

    You can then view the book by opening the `book/_build/html/index.html` file in your browser. Sometimes, you might need to clear the cache of your browser to see the changes or run the build command again. Also, note that if you have created a new file, you will need to add it to the `book/_toc.yml` file to see it rendered on the website.

4. **Submit pull request**

    Head over to Github and from the relevant branch in your fork, create a [Pull Request (PR)](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests).

    You can [request a PR review](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/requesting-a-pull-request-review) from someone. They will help with some feedback or might wholeheartedly agree with your changes. Others might also comment with their opinion. Add any necessary changes with subsequent commits to the same branch. Once everyone involved in this conversation is satisfied, the PR is merged. From personal experience though, frantically refreshing the browser every three seconds doesn't speed up the response rate of others. Sometimes, PRs can just take their own sweet time.

5. **Checking deployment**

    For the latest commit in your PR, you'll find that Github starts running some Actions to deploy these changes. If successful, you'll see green ticks. These changes are still not however to the main webpage. These are deployed to a "branch" of the webpage, which you can access at `https://geet-george.github.io/test-doc-pack/<your-branch-name>`. 

6. **... And that's it! Thanks for helping**

P.S. If something here doesn't work, or you have suggestions to improve this guide, feel free to submit an issue or PR. :)
