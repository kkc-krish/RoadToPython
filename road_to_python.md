# Introduction

Let's make a little index for learning Python. This should be useful for the new interns. It's a long post, with links to very long and dense articles. But if you read it all, I can assure you you will be totally confident with Python, and you're gonna love it!
Please, read at least:

* The basics
* Writing good Python
* Getting a Text Editor
* Code Style
* Structuring your project
* Virtualenv
* Python REPL/Interpreter
* Discovering and using an external library
* Nice pythonic tricks
* Troubleshooting

# The basics - First step
Start with Learning Python the Hard Way. It isn't perfect, but offers an excellent introduction to Python through practical examples and exercises (http://learnpythonthehardway.org/book/).

# Writing good Python
Learning Python the Right Way gives a good overview for the syntax and basics concepts, but that's not enough.
You should then read The Hitchhiker's Guide To Python. It is extremely complete, and will greatly improve the quality of your projects (http://docs.python-guide.org/en/latest/).

# Getting a Text Editor
Unless you're already confident with Vim or Emacs (or you want to try it), my advice is Sublime Text.
You need to configure it for python: http://piotr.banaszkiewicz.org/blog/2013/08/24/sublime-text-3-for-python-de… .
This link is good too, although some tools look a bit outdated against the previous link: http://dbader.org/blog/setting-up-sublime-text-for-python-development.

You may as well get a complete IDE, but I can't really advice you on this topic.
For once, don't refer to The Hitchhiker's Guide To Python's dedicated section (http://docs.python-guide.org/en/latest/dev/env/). It is quite useless, and I don't really agree with their settings on Vim.

# Code style
Please have a look at http://docs.python-guide.org/en/latest/writing/style/ (from The Hitchhiker's Guide To Python) to understand better the concepts.

The most important is: get a pylinter on your text editor! It will give you warnings when you don't respect Python's style conventions. It's a bit annoying at first, but when you comply to these conventions and get used to it, you're gonna love it ;).

Lines should be cut up to 79 characters. This is really annoying at first, but again it has a good payload. Here are a few tricks: http://docs.python-guide.org/en/latest/writing/style/#line-continuations

# Structuring your project
Again, you should refer to The Hitchhiker's Guide to Python: Structuring your project (http://docs.python-guide.org/en/latest/). And more specific sections:

    Documentation (http://docs.python-guide.org/en/latest/writing/documentation/)
    Testing your code (http://docs.python-guide.org/en/latest/writing/tests/)
    Packaging (http://docs.python-guide.org/en/latest/shipping/packaging/)

Also, read carefully Open Sourcing a Python Project The Right Way (http://www.jeffknupp.com/blog/2013/08/16/open-sourcing-a-python-project-the…). It's not bounded to Open Source (even though Open Source IS cool), and describes every necessary tools for a clean project.

# Virtualenv
This is really important. Don't make a project without virtualenv : it's gonna mess up your environment, and turn to an even bigger mess when collaborating.
Virtualenv let's you create one (or several) virtual environment specific for your project. This way, any library you would install as dependency for your project will be bounded to your project, rather than install system-wide.
It also makes it easier to deal with Python2/Python3 issues, and to test deployment scripts.
Here again, it is described in The Hitchhiker's Guide to Python (http://docs.python-guide.org/en/latest/dev/virtualenvs/) and Open Sourcing a Python Project The Right Way.

Here is also a nice trick: https://coderwall.com/p/2t36-q

Also, be careful that your Text Editor and your Python Interpreter are aware of your Virtualenv (and that they don't run your code with system-wide environment).

# Python Interpreter/REPL

(If you don't know what REPL stands for, it's basically what you experience with command-line, where you type a command and get an answer: http://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop)

Forget about the default Python's REPL. It sucks!
Instead, switch to IPython. It just does the same as the standard Python REPL, but in a much nicer way. And for more complicated prototyping, use IPython Notebook, there is almost no learning curve, and it's amazingly powerful! You can have a little overview here: http://pyvideo.org/video/2195/ipython-notebook-demo

To run a notebook with virtualenv:

    python -m IPython notebook --pylab=inline


# Python2 vs. Python3
Well, that's a tricky topic, and quite shameful actually. In one sentence : Python2 isn't compatible with Python3 ! So, do we use Python2.7, or Python3.3 ?
Well, as much as possible, use Python3. But if you depend on a lib that does not exist in Python3, and that it is too hard to adapt it, you may switch to Python2.
To easily export Python2 into Python3, use 2to3 tool (https://docs.python.org/2/library/2to3.html).
When coding, please make the code compatible with both, as explained in Supporting Python 2 and 3 without 2to3 conversion (http://python3porting.com/noconv.html).

# Debugging:
Don't debug your code using print, you can do much cooler: use python logging facilities. Have a look at this Python Logging Tutorial (https://pingbacks.wordpress.com/2010/12/21/python-logging-tutorial/)
There is also a Python debugger, PDB (https://docs.python.org/2/library/pdb.html), but so far I have never used it. You may give it a try.

# Discovering and using an external library
Start with installing the library:

    pip install <my_lib>

You should first make sure you have activated your virtualenv (workon ...).
Then, the most important when you discover a library is to read the doc. Python external libraries usually have some great documentation on ReadTheDoc, make good use of it. When you discover a library, the best is to have the documentation/getting started on one screen, an IPython Notebook on the other screen, and to execute the code as you read it.

# From Java to Python:
Many of us have started programming with Java, and the switch to Python isn't always straightforward. As for me, the biggest difference is that in Java "everything is part of an object", whereas in Python "everything is an object", but some code can be executed straight from a module (although technically, a module is an object, but nevermind this...).
I didn't find much documentation, but have a look at this StackExchange: http://programmers.stackexchange.com/a/47529.

# Nice Pythonic tricks
None of these tricks are absolutely required for coding in Python. But they greatly improve its quality. You can first code without knowing them, but as you go on with learning Python, you should really learn them. Not only because you may use it yourself, but also because you will surely have to handle some of them, from some external libraries.
## Decorators:
Decorators are really cool, and you need at least to know what they stand for (as you'll probably find it in some libraries). The best way to understand decorators is from Understanding Python decorators in 12 easy steps (http://simeonfranklin.com/blog/2012/jul/1/python-decorators-in-12-steps/). To go deeper, read Improve your Python skills: Decorators explained (https://www.jeffknupp.com/blog/2013/11/29/improve-your-python-decorators-ex…) from Jeff Knupp (a great Python blogger, I reference several of his articles if you notice).
## Generators:
Generators are stuffs about the yield keyword (that you may have seen in some codes). It's like really a powerful iterator, and may turn really to useful to, well, generate and publish content. Again we turn to Jeff Knupp for Improve your Python: Yield and Generators explained (https://www.jeffknupp.com/blog/2013/04/07/improve-your-python-yield-and-gen…).
## Exceptions (and duck typing):
The Official Python Doc gives clear explanation about exceptions: https://docs.python.org/3.4/tutorial/errors.html. To go deeper, once again, let's look at our friend Jeff Knupp, with Write Cleaner Python: Use exceptions (https://www.jeffknupp.com/blog/2013/02/06/write-cleaner-python-use-exceptio…). You have to know that exceptions are a good pattern in Python, and that they don't solely handle errors. For a complete list of built-in exceptions: https://docs.python.org/3.4/library/exceptions.html#exception-hierarchy.
## Context Managers:
Exceptions are useful, but dealing with try: open(); do_stuffs() except:... finally: close() all the time is boring. Python offers the with statement to make processes with a context. Read The Python "with" Statement by Example (http://preshing.com/20110920/the-python-with-statement-by-example/) to learn about it.
## Class methods, static methods and abstract methods:
Have a look at The definitive guide on how to use static, class or abstract methods in Python (http://julien.danjou.info/blog/2013/guide-python-static-class-abstract-meth…). That's all really useful, and be careful not to be confused with Java (the names are same, but the concepts are really different!
## One-liners:
Python is also famous for its one-liners. You don't need to do as good as these Powerful one-liners (https://wiki.python.org/moin/Powerful%20Python%20One-Liners), but try to use these syntax sugars tools:

* To easily loop in with iterators, use List Comprehension (http://www.pythonforbeginners.com/lists/list-comprehensions-in-python/).
* To create function as a one-liner, use Map or Lambda (http://www.u.arizona.edu/~erdmann/mse350/topics/list_comprehensions.html).
* For conditional structures, use  Ternary Operators (http://www.pythoncentral.io/one-line-if-statement-in-python-ternary-conditi…).

Use these one-liners anytime you can, as it makes your code much cleaner.

# Advanced tricks: Deeply understanding Python
These few links are NOT necessary for you to code in Python. But they may help you in better understanding your code and debugging, or dealing with very generic pieces of code.
What about the explicit self in classes ? Why explicit self has to stay (http://neopythonic.blogspot.fr/2008/10/why-explicit-self-has-to-stay.html) from Guido Van Rossum (the creator of Python) gives good explanation about the importance of explicit self. It looks weird at first, but it is actually a very good design.
Understanding what's going on: Well, that's very technical, with no practical application, but know about the actual memory handling in Python may save your debugging, sometimes. Drastically Improve your Python: Understanding Python's Execution Model (https://www.jeffknupp.com/blog/2013/02/14/drastically-improve-your-python-u…)
Dynamic Typing: In case you have to dynamically create a class. It is unusual, but it happens. To do so, you'll play with the very type of classes, named... Type! It is explained in Improve your Python: Metaclasses and Dynamic Classes with Type (https://www.jeffknupp.com/blog/2013/12/28/improve-your-python-metaclasses-a…).
Misc. You may also have fun reading about Hidden features of Python in this StackOverflow post: http://stackoverflow.com/questions/101268/hidden-features-of-python. But if you've reached that far in my post, you probably know most of them already ;).

# Scientific Programming:
Scientific Programming is a huge topic, and it would require a whole document as itself !
Basically, use IPython Notebook (described above) for coding, it works great with a scientific workflow.
Then, start with Numpy, it grants vectorial programming capabilities to python, same as in matlab. For example, you can describe a function like y = 6 * x ** 2 / np.sqrt(x), define x as an interval [min, max], and you'll get y(x).
You can then display data and functions with matplotlib. Check J.R. Johansson's tutorial Matplotlib - 2D and 3D plotting in Python (that's actually an IPython document): http://nbviewer.ipython.org/github/jrjohansson/scientific-python-lectures/b….
If you have to deal with datasets, use Pandas, it provides a DataFrame structure and improves Numpy. That's particularly good for dealing with Time Series.
And finally, if you're looking for any scientific tool (Machine Learning, Stats, Logic...), have a look at SciPy.

# TroubleShooting:
If you're facing some bugs, don't worry: Python has a great community ready to help you. Depending on the source of your problem, you should look at different places:
##General problem with Python:

* Start by searching on the Python Official Documentation, it is usually very complete (https://docs.python.org/3.3/index.html)
* If your problem is a bit more "philosophic", check the Python Enhancement Proposals (PEPs): http://legacy.python.org/dev/peps/
* No matter what you want to do, you will always find good answers on StackOverflow. Not only about fixing your problem, but also about the most pythonic way to do it.

## Problems specific with a library:

* Well, first of all, make sure you have read the whole documentation! Seriously, RTFM, Read The F.... Manual! One great aspect of Python community is that they usually develop clean libraries, with a great documentation, so you should make good use of it. You should find your library's documentation on ReadTheDocs (https://readthedocs.org/).
* Most Python project are hosted on GitHub, so you may directly ask to the contributors by creating an issue (or checking existing issues).
* If there is an actual bug in the library, or some feature you would like to see implemented, you may also consider to fork the library and implement what you need.