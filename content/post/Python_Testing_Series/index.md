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
If you have been to a car show room, you've probably bumped into a sales person who has tried to sell you car by emphasizing how good it performed in Crash tests. The same goes for Software development, if the software comes well tested, the users will feel comfortable to use it for their business. This is why its important that we get ourselves in a habit of writing tests when coding our projects. 

As A. Scopatz and K. D.Huff put it in their book _Effective Computation in Physics_, 2015,  pg. 403 _"Code is assumed guilty until proven innocent. This applies to software written by other people, but even more so to software written by yourself. The mechanism that builds trust that software is performing correctly is called testing."_
 
Indeed, if you're looking for any programming job especially jobs that have python as a requirement. Having tested projects is a major advantage. One way job seekers without commercial experience can show professional discipline is by ensuring that they test their projects before uploading them to remote repositories. This will also make it easy for you to join companies that use Test Driven Development methodology because you test your code and you learn every-time you do it.

## Conventions.

Now is the time to talk about conventions in testing especially Python testing. The're many conventions for testing, some developers embed there tests in the code as they code i.e including assertions and exceptions, this is the minimum effort required to ensure that you code runs well. The other two ways of going about it, involve having separate files for the source code and the test files or having test files in the same folder as the source code. This is in fact used on top of the first option. The last two options differ only on where the test files are placed.
In both of the last two conventions we use the _same naming style_, I have to emphasize this we must follow the _naming_ convention in python testing because if we get it wrong the test will not run.  

## What we need before we begin?
As of this writing, these are the requirements one would need to have in order to guarantee success with this walk through.

- Python 3+ (If you don't already have it.) 
- Jupyter (I recommend Anaconda distribution if you don't have this one either)
- Lastly, a text editor of your choice (I recommend Visual Studio code by Microsoft)

Once you get above list on your machine you can go head and open you text editor and follow the procedure for creating  a new folder, if you're using cmd/Shell/Terminal and just type ``` mkdir``` followed by whatever name you feel appropriate. I shall name mine python_testing. 
Create another sub folder within the python_testing parent folder and name it Text_Editor folder, this sub folder can be optional if you don't like to have many folders in your environment.

I am going to conclude this post here because its becoming long, I keep my articles short so that they're easily digestable. Hopefully I was able to whet your appetite, keep an eye out for part two of this series where we shall begin with learning how to use those conventions starting with creating folders and learning how to unittest our code in an editor and later in Jupyter notebooks. I apologies for the long post, I appreciate you spending on my reading my articles. Keep Learning!.
