# What is Python (Programming)? - The Basics

Before getting started, lets get familiarized with the language first.

Python is a general-purpose language. It has wide range of applications from Web development (like: Django and Bottle), scientific and mathematical computing (Orange, SymPy, NumPy) to desktop graphical user Interfaces (Pygame, Panda3D).

The syntax of the language is clean and length of the code is relatively short. It's fun to work in Python because it allows you to think about the problem rather than focusing on the syntax.

**More information on Python Language:**

## History of Python

Python is a fairly old language created by Guido Van Rossum. The design began in the late 1980s and was first released in February 1991.

## Why Python was created?

In late 1980s, Guido Van Rossum was working on the Amoeba distributed operating system group. He wanted to use an interpreted language like ABC (ABC has simple easy-to-understand syntax) that could access the Amoeba system calls. So, he decided to create a language that was extensible. This led to design of a new language which was later named Python.

## Why the name Python?

No. It wasn't named after a dangerous snake. Rossum was fan of a comedy series from late seventies. The name "Python" was adopted from the same series "Monty Python's Flying Circus".

## Features of Python Programming

1. A simple language which is easier to learn
   Python has a very simple and elegant syntax. It's much easier to read and write Python programs compared to other languages like: C++, Java, C#. Python makes programming fun and allows you to focus on the solution rather than syntax.
    If you are a newbie, it's a great choice to start your journey with Python.
2. Free and open-source
    You can freely use and distribute Python, even for commercial use. Not only can you use and distribute softwares written in it, you can even make changes to the Python's source code.
    Python has a large community constantly improving it in each iteration.
3. Portability
    You can move Python programs from one platform to another, and run it without any changes.
    It runs seamlessly on almost all platforms including Windows, Mac OS X and Linux.
4. Extensible and Embeddable
    Suppose an application requires high performance. You can easily combine pieces of C/C++ or other languages with Python code.
    This will give your application high performance as well as scripting capabilities which other languages may not provide out of the box.
5. A high-level, interpreted language
    Unlike C/C++, you don't have to worry about daunting tasks like memory management, garbage collection and so on.
    Likewise, when you run Python code, it automatically converts your code to the language your computer understands. You don't need to worry about any lower-level operations.
6. Large standard libraries to solve common tasks
    Python has a number of standard libraries which makes life of a programmer much easier since you don't have to write all the code yourself. For example: Need to connect MySQL database on a Web server? You can use MySQLdb library using import MySQLdb .
    Standard libraries in Python are well tested and used by hundreds of people. So you can be sure that it won't break your application.
7. Object-oriented
    Everything in Python is an object. Object oriented programming (OOP) helps you solve a complex problem intuitively.
    With OOP, you are able to divide these complex problems into smaller sets by creating objects.

## Applications of Python

**Web Applications**

You can create scalable Web Apps using frameworks and CMS (Content Management System) that are built on Python. Some of the popular platforms for creating Web Apps are: Django, Flask, Pyramid, Plone, Django CMS.

Sites like Mozilla, Reddit, Instagram and PBS are written in Python.

**Scientific and Numeric Computing**

There are numerous libraries available in Python for scientific and numeric computing. There are libraries like: SciPy and NumPy that are used in general purpose computing. And, there are specific libraries like: EarthPy for earth science, AstroPy for Astronomy and so on.

Also, the language is heavily used in machine learning, data mining and deep learning.

**Creating software Prototypes**

Python is slow compared to compiled languages like C++ and Java. It might not be a good choice if resources are limited and efficiency is a must.

However, Python is a great language for creating prototypes. For example: You can use Pygame (library for creating games) to create your game's prototype first. If you like the prototype, you can use language like C++ to create the actual game.

**Good Language to Teach Programming**

Python is used by many companies to teach programming to kids and newbies.

It is a good language with a lot of features and capabilities. Yet, it's one of the easiest language to learn because of its simple easy-to-use syntax.

## Reasons to Choose Python as First Language

1. Simple Elegant Syntax

    Programming in Python is fun. It's easier to understand and write Python code. Why? The syntax feels natural. Take this source code for an example:

    ```py
    a = 2
    b = 3
    sum = a + b
    print(sum)
    ```

    Even if you have never programmed before, you can easily guess that this program adds two numbers and prints it.

2. Not overly strict

    You don't need to define the type of a variable in Python. Also, it's not necessary to add semicolon at the end of the statement.

    Python enforces you to follow good practices (like proper indentation). These small things can make learning much easier for beginners.

3. Expressiveness of the language

    Python allows you to write programs having greater functionality with fewer lines of code. Here's a link to the source code of Tic-tac-toe game with a graphical interface and a smart computer opponent in less than 500 lines of code. This is just an example. You will be amazed how much you can do with Python once you learn the basics.

4. Great Community and Support

    Python has a large supporting community. There are numerous active forums online which can be handy if you are stuck. Some of them are:

    - Learn Python subreddit
    - Google Forum for Python
    - Python Questions - Stack Overflow
  
## Run Python on Your Operating System

You will find the easiest way to run Python on your computer (Windows, Mac OS X or Linux) in this section.

### Install and Run Python in Mac OS X

1. Go to Download Python page on the official site and click Download Python 3.6.0 (You may see different version name).
2. When the download is complete, open the package and follow the instructions. You will see "The installation was successful" message when Python is successfully installed.
3. It's recommended to download a good text editor before you get started. If you are a beginner, I suggest you to download Sublime Text. It's free.
4. The installation process is straight forward. Run the Sublime Text Disk Image file you downloaded and follow the instructions.
5. Open Sublime Text and go to File > New File (Shortcut: Cmd+N). Then, save (Cmd+S or File > Save) the file with .py extension like: hello.py or first-program.py
6. Write the code and save it again. For starters, you can copy the code below:
    
    ```py
    print("Hello, World!")
    ```

    This simple program outputs "Hello, World!"
7. Go to Tool > Build (Shortcut: Cmd + B). You will see the output at the bottom of Sublime Text.Congratulations, you've successfully run your first Python program.

### Install and Run Python in Linux (Ubuntu)

### Install and Run Python in Windows

## Your First Python Program

Often, a program called "Hello, World!" is used to introduce a new programming language to beginners. A "Hello, World!" is a simple program that outputs "Hello, World!".

However, Python is one of the easiest language to learn, and creating "Hello, World!" program is as simple as writing print("Hello, World!"). So, we are going to write a different program.

### Program to Add Two Numbers

```py
    # Add two numbers
    num1 = 3
    num2 = 5
    sum = num1+num2
    print(sum)
```

#### How this program works?

**Line 1:** # Add two numbers

Any line starting with # in Python programming is a comment.

Comments are used in programming to describe the purpose of the code. This helps you as well as other programmers to understand the intent of the code. Comments are completely ignored by compilers and interpreters.

**Line 2:** num1 = 3

Here, num1 is a variable. You can store a value in a variable. Here, 3 is stored in this variable.

**Line 3:** num2 = 5

Similarly, 5 is stored in num2 variable.

**Line 4:** sum = num1+num2

The variables num1 and num2 are added using + operator. The result of addition is then stored in another variable sum.

**Line 5:** print(sum)

The print() function prints the output to the screen. In our case, it prints 8 on the screen.

### Few Important Things to Remember

To represent a statement in Python, newline (enter) is used. The use of semicolon at the end of the statement is optional (unlike languages like C/C++, PHP). In fact, it's recommended to omit semicolon at the end of the statement in Python.

Instead of curly braces { }, indentations are used to represent a block.

```py
   im_a_parent:
        im_a_child:
            im_a_grand_child
        im_another_child:
            im_another_grand_child
```