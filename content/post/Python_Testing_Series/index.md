+++
title = "Python_Testing_Series"
subtitle = ""

# Add a summary to display on homepage (optional).
summary = "Testing your code is a must not an option, the more you do it the more you come to enjoy it and the more you become good at it"

date = 2019-07-04T15:23:49+01:00
draft = false

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["MrRutledge"]

# Is this a featured post? (true/false)
featured = false

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Testing","Unit_Testing", "Python"]
categories = []

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["deep-learning"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
# projects = ["internal-project"]

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
[image]
  # Caption (optional)
  caption = ""

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = ""
+++

## Why you should always test your Python code?

Testing code is one of those things that some developers find laborious, this can be easily verified by anyone who has ever cloned a seemingly good repository from github only to find that most of the code doesn't work.
In this post we shall work through examples, while learning how to use the standard testing library for Python. The post is mainly aimed at anyone interested to learn how to include tests in the code and how to go about it.
There are many test libraries for Python, nose, pytest, unittest etc. In this post however, we shall stick to unittest because it's easily accessible, it comes installed with Python and once you understand it you can easily adapt the concepts to other libraries.

#### What you should be comfortable with by the end of this walk through series?

I hope you'll be able to explain the process of writing a unittest for python programs and also be able to run tests on your Python Jupyter Notebook.

## Motivation.
If you have ever been to a car show room, you know this feeling, the moment walked in you were approached by a sales person who tried to sell you a car by emphasizing how good it performed in crash tests. The same goes for software development, if the software comes well tested, the users will feel comfortable to use it for their business. This is why its important that we get ourselves in a habit of writing tests when we're working on our projects. 

As A. Scopatz and K. D.Huff put it in their book _Effective Computation in Physics_, 2015,  pg. 403 _"Code is assumed guilty until proven innocent. This applies to software written by other people, but even more so to software written by yourself. The mechanism that builds trust that software is performing correctly is called testing."_
 
Indeed, if you're looking for any programming job especially jobs that have python as a requirement. Having tested projects is a major advantage. One way job seekers without commercial experience can show professional discipline is by ensuring that they test their projects before uploading them to remote repositories. This will also make it easy for you to join companies that use Test Driven Development methodology because you test your code and you learn every-time you do it.

##  Testing Conventions.

Now is the time to talk about conventions in testing especially Python testing. There are many conventions for testing, some developers embed there tests in the code as they code i.e including assertions and exceptions, this is the minimum effort required to ensure that you code runs well after debbuging. The other two ways of going about it, involve having separate files for the source code and the test files or having test files in the same folder as the source code. This is in fact used on top of the first option. The last two options differ only on where the test files are placed.
In both of the last two conventions we use the _same naming style_, I have to emphasize this we must follow the _naming_ convention in python testing because if we get it wrong the test will not run.  

## What we need before we begin?
As of this writing, these are the requirements one would need to have in order to guarantee success with this walk through.

- Python 3+ (If you don't already have it.) 
- Jupyter (I recommend Anaconda distribution)
- Lastly, a text editor of your choice (I recommend Visual Studio code by Microsoft)

Once you get above list on your machine you can go head and open you text editor and follow the procedure for creating  a new folder, if you're using cmd/Shell/Terminal and just type ``` mkdir``` followed by whatever name you feel appropriate. I shall name mine python_testing. 
Create another sub folder within the python_testing parent folder and name it Text_Editor folder, this sub folder can be optional if you don't like to have many folders in your environment.

So far your folder should be python_testing ---> text_Editor, we shall begin with easy tests like summing and subtracting numbers. While in the text_editor file go ahead and create a new file and call it _calc.py_. This is where we shall put all our coding to be tested, if you working on a large program then you might consider using the other convention of having separate folders for source code and testing code.
```python
#calc.py module

def add()
"""Addition function"""
        return  a + b
```
 Lets take the code above as an example, the function just sums the given variable. If we want to test this using the standard testing library we need to create another file, this is where the name convention comes in handy. If we want the testing library **Unittest** to see our test module we have to give it a particular name. In our case it will be _test_calc.py.  While in the _test_calc.py module write the following code:
```Python
#test_calc.py module

import unittest # imorting the library
import calc #importing the calc module we created earlier
 

# We need a class that will contain all the tests on different functions on a module.
class  testCalc(unittest.TestCase):
    """ All functions in the calc.py will be tested tested """
         def test_add(self):
              self.assertEqual(calc.add(10,6),16)

# this is only required if we want to run our module with python test_calc.py command
#if not included in the module you will have to run you code by python -m unittest test_calc.py
if __name__== '__main__':
        unittest.main()

```
The above code block is the minimum code required in order to test the code we wrote earlier. We can run the above code to see the results in the terminal, you should see one point/period indicating that it ran one test and an OK at the bottom. I have included a copy of test code in my [repo](https://github.com/MrRutledge/MrRutledgeHub/tree/master/content/post/Python_Testing_Series) in case something goes wrong with your code you can correct it by looking at my repository.
We can add on other checks for example, we can check if the function will perform on negative values and positive values and produce the right answer. The technical term for that is _testing edge cases_

  ```Python
import unittest # imorting the library
import calc #importing the calc module we created earlier
 

# We need a class that will contain all the tests on different functions on a module.
class  testCalc(unittest.TestCase):
    """ All functions in the calc.py will be tested tested """

            def test_add(self):
              self.assertEqual(calc.add(10,6),16)
              self.assertEqual(cal.add(-10,-6),-16)
              self.assertEqals(calc.py(10,-3),7)
```

This is enough  code for now, lets dig a bit deeper into the code we have written so far, Unittest library has a variety of methods, you need to have a look at the [documentation](https://docs.python.org/3/library/unittest.html#module-unittest) to have a clear understanding of all the methods but we can have a quick view of the widely used methods in the library and what they do.

| Method              |   Checks that  |
|---------------------|----------------|
|assertEqual(a, b)    |   a == b       |
|assertNotEqual(a, b) | a != b         |
|assertTrue(x)        |bool(x) is True |
|assertFalse(x)       |bool(x) is False|
|assertIs(a, b)       |a is b          |
|assertIsNot(a, b)    |a is not b      |
|assertIsNotNone(x)   |x is not None   |
|assertIn(a, b)       |a in b          |
|assertNotIn(a, b)    |a not in b      |
Table from the documentation.

I am going to conclude this post here because its becoming long, I keep my articles short so that they're easily digestable. Hopefully I was able to whet your appetite for python testing, keep an eye out for part two of this series where we shall begin with learning how to raise exceptions in tests and how to unit test our code in an editor and later in Jupyter notebooks.
I apologies if there is any mistake in this post, please alert it me if you see any, I appreciate you spending some time reading my articles. Keep Learning!.
