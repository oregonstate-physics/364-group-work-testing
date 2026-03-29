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
The default experience of coding on Windows is downright abysmal. 
This is why the omniscient developers at ~Microslop~ Microsoft have decided that the best way to develop on windows is to use Linux. Specifically, the Windows Subsystem for Linux (WSL). 
#### Installing WSL2 on Windows
Open PowerShell as Administrator and run (type all of the commands in this document manually, do not copy and paste):
```
wsl.exe --list --online
```
To list the distributions and versions of linux available to you. At the time of writing, the most appro    priate distribution should be Ubuntu 24.04 LTS.
 
```
wsl --install [distro]
```
Once it is downloaded, launch it like you would a normal application. If you have Windows 11, it *should* just work, where you can start and run applications in their GUI form. There might be some ironing out that needs to be done.
### Mac
Most versions of Mac will already have git installed, and you can activate it through the terminal simply by typing `git version`. However, if you don't have git installed for whatever reason, you can install the latest version using [Homebrew](brew.sh):
```
brew install git
```
### Linux
If you are using Linux, congratulations! You already have git on your computer and are probably ahead of the curve.

## Class Resources
There are several resources you can access to understand how to navigate the software we will use in this class. It is expected that you will be able to not only find but also understand technical documentation for the software packages you are using; stackexchange can only get you so far! 

You should take some time to familiarize yourself with these websites that explain the software you are using:

* https://git-scm.com/
* https://docs.github.com/en/get-started/git-basics
* https://jupyter-notebook.readthedocs.io/en/latest/
* https://docs.github.com/en/get-started/start-your-journey

## Effective Software Development Practices
One of the most important things you should internalize as a scientific software developer is that *you are in control of the knowledge*. 
Just as you may have been confused and frustrated by poor documentation in the past, people who may use your software will be confused and frustrated with your lack of communication. 

There are several style guides that you can follow as a software developer. The most important thing is that you choose one and *stick with it*. The preferred style for this class is the [Numpy Style](https://numpydoc.readthedocs.io/en/latest/format.html). This is the style of choice for a large portion of scientific software packages. 

As you grow to write effective documentation inside your code, you will notice that the effort you give will pay off in dividends: IDEs like VSCode will automatically format and provide real time context of your functions based on your docstrings, and people can pick up from where you left off with little to no person-to-person training.

> [!IMPORTANT]
> AI is not particularly good at writing documentation, especailly for advanced functions. Use a template and fill it out yourself.

#### Anatomy of a function
A python function has several parts to it. Good documentation should be as concise as possible without leaving out any detail.
See the following example:
```python
def foo(bar):
    """This is a docstring.

    It can be spread over several lines.
    """
    return bar**2

```

There are several parts of a function that are important to legibility and good communication. 
The given example can be improved in a couple of different ways. 
The first is the function and variable names `foo` and `bar`. 
This should be a bit more descriptive of what is actually happening. 
Remember that naming things well doesn't cost anything and is only helpful!

```python
def squared(number): 
    """This is a docstring.

    It can be spread over several lines.
    The first line should start with a verb and explain concisely what the
    function does. The rest of the docstring should describe what the 
    function does in more detail if necessary.

    Parameters
    ----------
    number : int 
        Description of `number`.

    Returns
    -------
    number^2 : int
        Description of `number^2`.

    """
    return number**2 
```
