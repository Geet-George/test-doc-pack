# Testing

When we write code, we want to make sure it works as expected. We can do this by writing tests. Tests are just Python functions that we run to check if our code performs as expected.

Here, we'll learn how to write tests for our code. We'll start with writing tests using `if` conditions, then move on to using `assert`, and finally, we'll learn how to use `pytest`, a testing framework that makes it easy to write and run tests. In between, we'll also learn about edge cases and test-driven development. But let's start with a simple example.

## Testing with `if` (❌)

We'll start with defining a function called `biggest_change()`. What this function does is take a list of values of some variable (let's say daily temperature) and returns the biggest change in it.

Here's the function:

```python
import numpy as np

def biggest_change(array_of_values):
    differences = np.diff(array_of_values)
    return differences.max()
```

Make a new Python file and add the above code to it. Save the file with a name of your choice.

What the function does is calculate the difference between each element in the list and store it in a numpy array called `differences`. It then returns the maximum value in the array `differences`.
An obvious way to check if our function works well is to call it with some values and see if the result is what we expect. We know about `if` statements, let's use those to check. Below the function definition, add the following code:

```python
daily_temperature = [12, 13, 17, 18]
result = biggest_change(daily_temperature)
if result == 4:
    print("Test passed")
else:
    print("Test failed")
```

Now, execute the code by running `python3 <your-filename>.py` in the terminal. What output do you see? If our function works, we'll get the "Test passed" message and otherwise, we'll get "Test failed". For the list we provided as input to the function, the biggest change is indeed 4, so the test should pass. Great! But what if we have negatives in the list, i.e. when temperatures are lower the next day? Our function should still work, right? Let's test it. Add the following code below the previous test (don't replace our previous test):

```python
daily_temperature = [12, 14, 10, 11]
result = biggest_change(daily_temperature)
if result == 4:
    print("Test passed")
else:
    print("Test failed")
```

What output do you see now? The second test failed, right? If we revisit our function, we see that it returns the maximum value in the list. In this case, the maximum value is 2, not -4. However, what we want from our function is really the magnitude of the biggest change, be it positive or negative. So, our function doesn't work as expected. We need to fix it. We need to consider the absolute value of the numbers in the list. Let's update our function:

```python

def biggest_change(array_of_values):
    differences = np.diff(array_of_values)
    differences = np.abs(differences)
    return differences.max()
```

We have now added a line that calculates the absolute value of the differences. This way, we get the magnitude of the changes, whether they are positive or negative. Now, run the tests again. You should see that both tests pass. This is how testing works. We write tests to check if our code works as expected. If the tests fail, we fix the code and run the tests again. We keep doing this until all tests pass. 

That said, we can make this whole process a lot better...

## Testing with `assert` (✅)

The way we have been testing with `if` conditions is quite cumbersome, because: 

1. We have to write long `if` conditions for every test we want to run. 

2. We have to read through the printed messages to know if the test passed or failed. 

There should be a better way to do this, right? It would be great if we are simply notified every time there is a failure, instead of having to read through all the printed messages from the `if` conditions and figuring out if a test failed or not.

Good news! We have something called `assert` in Python. `assert` is a statement that checks if a condition is true. If the condition is true, the program continues to run. If the condition is false, the program raises an `AssertionError` exception. We can use `assert` to write our tests, and you'll see that it becomes a lot easier than writing `if` conditions. Let's rewrite our previous tests using `assert` (replace the testing with the `if` conditions with the following code, don't remove the function definition):

```python
daily_temperature = [12, 13, 17, 18]
result = biggest_change(daily_temperature)
assert result == 4

daily_temperature = [12, 13, 10, 11]
result = biggest_change(daily_temperature)
assert result == 3
```

Now, run the code again. You'll see that there is no output. This is good. That's because the `assert` statement doesn't print anything if the condition is true. 

Let's see what happens when one of the tests fail. For this, we will go back to our original function by commenting out the line that calculates the absolute value of the differences:

```python
def biggest_change(array_of_values):
    differences = np.diff(array_of_values)
    # differences = np.abs(differences)
    return differences.max()
```

Now, run the code again. You'll see that the program raises an `AssertionError` exception. This is great, because now we didn't have to read through the printed messages to know if a test failed. We can see it right away. We now know that our function doesn't work as expected. We also know the fix for it. Simply uncomment the line where we calculate absolute idfferences. 

```python
def biggest_change(array_of_values):
    differences = np.diff(array_of_values)
    differences = np.abs(differences)
    return differences.max()
```

Now, run the code again. You'll see that all tests pass. That's how you can use `assert` to write tests for your code. It's a lot easier and cleaner than using `if` conditions. You can write as many tests as you want using `assert` and run them all at once. If any of the tests fail, you'll know right away.

## Edge-cases & Test-Driven Development

We haven't tested our function with an empty list yet. Add the following test below our tests:

```python
daily_temperature = []
result = biggest_change(daily_temperature)
assert result == None
```

Now, run the code again. You'll see that the program raises an exception. One nice thing we learn here is that by testing many different cases, we can find bugs in our code that we didn't think of before. In fact, it also forces us to decide what the function should do when the list is empty, something we didn't think of before. We can think of multiple things here, i.e. return `None`, raise an exception, ask the user to provide a non-empty list, etc. That's up to you to decide. But the point is that with more testing, especially edge cases, we can find these bugs and make our code better. 

For now, let's return `None` when the list is empty. Update the function as follows:

```python
def biggest_change(array_of_values):
    if not array_of_values:
        return None
    differences = np.diff(array_of_values)
    abs_differences = np.abs(differences)
    return abs_differences.max()
```

Now, run the tests again. You'll see that all tests pass. :)

Another edge case we can think of is when the list has only one element. What should our function do in this case? Should it return 0, because there is no change? Or should it return `None`? Again, that's up to you to decide. But let's say we want to return 0 in this case. Before we update the function, first let's add the following test below our existing tests:

```python
daily_temperature = [12]
result = biggest_change(daily_temperature)
assert result == 0
```

Now, run the tests. You'll see that the program raises an exception. This is because our function doesn't handle the case when the list has only one element. Let's update the function to handle this case:

```python
def biggest_change(array_of_values):
    if not array_of_values:
        return None
    if len(array_of_values) == 1:
        return 0
    differences = np.diff(array_of_values)
    abs_differences = np.abs(differences)
    return abs_differences.max()
```

Now, run the tests again. All tests pass. :)

What you just did is something software pros call "*test-driven development*" (ooh, look at you, using fancy software practices!). We first wrote the tests, we made our functions fail. Then, we wrote the code to make the tests pass. This is a good practice because it forces us to think about what the function should do in different cases before we write the code, which means that we are not just writing tests to confirm the functions that we just wrote, but actually checking if our functions do what we have in mind. 

Whether you want to do test-driven development or not is a personal choice and also depends a bit on the project you are working on. But in any case, it is a good practice to write tests for your code. It helps you catch bugs early and makes your code more robust. The more you code, the more you'll realise that the time spent writing tests is very little compared to the time you will save by catching bugs early and not having to dig through pieces of your code later to find out why it's not working.

## Using `pytest` for testing

Now, let's look at a more efficient way of running our tests instead of running our Python file every time. First, we'll add all our tests to a single function. Let's call it `test_biggest_change()`. Add the following code to the file and remove the tests (don't remove the function definition):

```python
def test_biggest_change():
    daily_temperature = [12, 13, 17, 18]
    result = biggest_change(daily_temperature)
    assert result == 4

    daily_temperature = [12, 13, 10, 11]
    result = biggest_change(daily_temperature)
    assert result == 3

    daily_temperature = []
    result = biggest_change(daily_temperature)
    assert result == None

    daily_temperature = [12]
    result = biggest_change(daily_temperature)
    assert result == 0
```

We haven't done anything too complicated. All we did was move our tests into a function. So, now if we call this function, all tests will run. Call the function by adding the following code at the end of the file:

```python
test_biggest_change()
```

Now, run the code. All we are doing is calling the `test_biggest_change()` function. Inside there, all of our tests are run one after the other. You'll see that all tests pass. Nice! 

But this is a simple example. In our real-world projects, we will have many functions and many tests for each function. We can't keep running the code and checking the result manually every time. That's where `pytest` comes in. `pytest` is a testing framework that makes it easy to write and run tests. In fact, you don't even need that function call at the end of the file. `pytest` will automatically find all the tests in your file, by searching for functions that start with `test_` and run them. So, now you can remove the line where you call the function `test_biggest_change()` at the end of your file. 

Now, let's try out `pytest`. Fisrt, install `pytest` by running the following command in the terminal:

```bash
pip install pytest
```

Once you have successfully installed `pytest`, you can run all your tests by simply running the following command in the terminal. 

```bash
pytest <your-filename>.py
```

Ahaa! What do you see? Is it something like this?

```bash
============================= test session starts ==============================
<your-platform-and-Python-details>
rootdir: <your-root-directory>
collected 1 item

<your-filename>.py .                                                      [100%]

============================== 1 passed in 0.05s ===============================
```

That's great! `pytest` automatically found all the tests in your file and ran them. Let's break down the output.

In the beginning of the output, you'll see some information about your platform and Python details, and the root directory you ran the tests in. This is unimportant for now. Then, you'll see the following:

1. `collected 1 item`: This tells us that `pytest` found 1 test in our file.
2. `<your-filename>.py .`: This tells us that the test passed. The `.` indicates that the test passed. If the test failed, you would see an `F` instead of a `.`.

Let's make another test function called `test_biggest_change_negative()` that tests our function with negative values and then intentionally make it fail by changing the expected result. Add the following code to the file:

```python
def test_we_want_to_see_what_a_pytest_fail_looks_like():
    daily_temperature = [12, 14, 10, 11]
    result = biggest_change(daily_temperature)
    assert result == 1
```

Now, run the tests again using `pytest <your-filename>.py`. You'll see that the test fails. You'll see an `F` instead of a `.`. The output will look something like this:

```bash
============================== test session starts ===============================
<your-platform-and-Python-details>
rootdir: <your-root-directory>
collected 2 items                                                                

<your-filename>.py .F                                               [100%]
==================================== FAILURES ====================================
_________________ test_we_want_to_see_what_a_pytest_fail_looks_like _________________

    def test_we_want_to_see_what_a_pytest_fail_looks_like():
        daily_temperature = [12, 14, 10, 11]
        result = biggest_change(daily_temperature)
>       assert result == 1
E       assert np.int64(4) == 1

<your-filename>.py:35: AssertionError
============================ short test summary info =============================
FAILED <your-filename>.py::test_we_want_to_see_what_a_pytest_fail_looks_like - assert np.int64(4) == 1
========================== 1 failed, 1 passed in 0.09s ===========================
```

The output tells us that `pytest` collected 2 items (2 tests, we have two `test_` functions now) and that 1 test failed. It also tells us which test failed and why. The fact that pytest can find your test functions and run them and notify you of test performances makes it so much more efficient than running the code manually every time. 

## Conclusion

This is just a small introduction to `pytest`. There are many more features in `pytest` that you can explore. You can write tests in separate files, you can run tests in parallel, you can run tests in a specific order, you can run only a specific test, you can run tests in a specific directory, and many more. You can find more information about `pytest` [in their documentation](https://docs.pytest.org/en/stable/index.html).

That's it as an introduction to testing! You now know how to write tests for your code and run them using `pytest`. Happy testing! 🧪

-----

P.S. The test function we wrote here, for the sake of ease of understanding, was not written too concisely. A better framing of the test function would be:

```python
def test_biggest_change():
    assert biggest_change([12, 13, 17, 18]) == 4
    assert biggest_change([12, 13, 10, 11]) == 3
    assert biggest_change([]) == None
    assert biggest_change([12]) == 0
```
