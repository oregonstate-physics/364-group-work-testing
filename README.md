# PH 364
## Welcome!

Welcome to PH 364! 

## Table of Contents
1. [Introduction](#introduction)
2. [Setting Up Your Laptop](#setting-up-your-laptop)
3. [Class Resources](#class-resources)
4. [Effective Software Development Practices](#effective-software-development-practices)

## Introduction

## Setting Up Your Laptop
For the majority of the class, assignments will be via JupyterHub. 
### Windows
If you have a windows computer, please take a look at [Setting up WSL on Windows](windows.md).
### Mac
### Linux

## Class Resources
There are several resources you can access to understand how to navigate the software we will use in this class. It is expected that you will be able to not only find but also understand technical documentation for the software packages you are using; stackexchange can only get you so far! 

You should take some time to familiarize yourself with these websites that explain the software you are using:

* https://git-scm.com/
* https://docs.github.com/en/get-started/git-basics
* https://jupyter-notebook.readthedocs.io/en/latest/
* 

## Effective Software Development Practices
One of the most important things you should internalize as a scientific software developer is that *you are in control of the knowledge*. 
Just as you may have been confused and frustrated by poor documentation in the past, people who may use your software will be confused and frustrated with your lack of communication. 

There are several style guides that you can follow as a software developer. The most important thing is that you choose one and *stick with it*. The preferred style for this class is the [Numpy Style](https://numpydoc.readthedocs.io/en/latest/format.html). This is the style of choice for a large portion of scientific software packages. 

As you grow to write effective documentation inside your code, you will notice that the effort you give will pay off in dividends: IDEs like VSCode will automatically format and provide real time context of your functions based on your docstrings, and people can pick up from where you left off with little to no person-to-person training.

#### Anatomy of a function
A python function has several parts to it. Good documentation should be as concise as possible without leaving out any detail.
See the following example:
```python
def foo(bar):
    """This is a docstring.

    It can be spread over several lines.
    The first line should start with a verb and explain concisely what the 
    function does. The rest of the docstring should describe what the 
    function does in more detail if necessary.

    Parameters
    ----------
    bar : int 
        Description of `bar`.

    Returns
    -------
    bar^2 : int
        Description of `bar^2`.

    """
    return bar**2

```
