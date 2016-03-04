## 1. Introduction to Python

### 1.1 About Python
_Python_ is a general purpose, high-level programming language.
It puts a lot of emphasis on code readability and productivity.  
It is very beginner friendly but also used for large scale, real world projects.  
The official site is http://www.python.org. Here we can find the official documentation and python distributions for download.

### 1.2 About this course and prerequisites
This is an introduction to the Pyhon language for beginners.
Some familiarity with programming will help, but you don't have to be a programmer to follow this course.  

### 1.3 Setting-up
#### 1.3.1 Install Python
This course uses _Python 3.5_
In order to follow it you will need to install _Python 3.5.x_ (or greater).
Python is available on the official site (http://www.python.org), but I recommend to use the [_miniconda_ distribution](http://conda.pydata.org/miniconda.html).
Now, verify that everything installed fine.  
Open a _terminal_ (also known as _Command Prompt_ on Windows systems) and execute:

    python

You should see something similar to:

    Python 3.5.1 |Continuum Analytics, Inc.| (default, Dec  7 2015, 11:17:45)
    [GCC 4.4.7 20120313 (Red Hat 4.4.7-1)] on linux
    Type "help", "copyright", "credits" or "license" for more information.
    >>>

You have invoked the Python _interactive shell_.
Here you can introduce commands at the interactive prompt (>>>) and the Python _interpreter_ will execute them.  
For example, you can enter some arithmetic expressions and use Python as a calculator:

    >>> 2 * 8 + 4
    20

Call the quit function to exist the interactive shell:

    >>> quit()

#### 1.3.2 Install IPython
_IPython_ it is an improved interactive shell.
In order to install it, we will use the _pip_ package management utility.  
From a _terminal_, execute:

    pip install ipython

Note: on Windows systems you will also need to install the _pyreadline_ package in order to benefit from color highlighting and auto-complete when using _ipython_:

    pip install pyreadline ipython

#### 1.3.3 Install code checking tools
During this course we will use the _pylint_ static code checking tool. Install it as usually:

    pip install pylint

### 1.4 Text editors and Integrated Development Environments
You will need a _text editor_ or an _Integrated Development Environment_ (_IDE_) with Python support.
For beginners, I recommend a text editor. There are a lot of possible options you can choose from.  
On Windows systems, you can install [_Notepad++_](https://notepad-plus-plus.org/).
Linux systems usually comes with programmers editors already installed. Otherwise, you can install one such as _Geany_, _Gedit_, _Kate_, _vim_, etc.  
In case that you want to use an _IDE_, I recommend [_PyCharm_](https://www.jetbrains.com/pycharm/download/) or [_PyDev_](http://www.pydev.org/).
