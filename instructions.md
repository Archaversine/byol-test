---
author: rbose
title: Build Your Own Programming Language
---

# Introduction

-   Due Date: September 28

In this assignment, we will be building our own elementary programming
language. We will start by verbally describing the language's syntax. We
will then explicitly define a grammar to read the syntax in Backus-Naur
form using the ANTLR parser generator to create the basic code to read
our language. We will finally write an interpretter which will walk
through the abstract syntax trees generated by ANTLR and execute our
programs.

## Content Goals

-   Describe and define language syntax. Consider practical design
    decisions that can impact language usability and implementation.
-   Examine and understand abstract syntax trees
-   Implement an interpretter to execute your programming language in a
    simple environment
-   Write test cases for your language
-   Read and understand primary documentation from an open source
    project
-   Provide documentation for your language

## Parallel goals

-   Fork, commit, and push to a git repo
-   Receive comments on code via github
-   Handle potential git conflicts
-   Begin to learn about runtime environments, paths, and other terminal
    concepts. (This will actually be an explicit goal later in the class
    and is one of the most important core competencies imo)

# Running things locally and online

It is up to you to figure out how to run your code locally. You will
need to install `antlr` and use it to generate the python template once
you have created your grammar.

However, I have set up an environment that will allow you to run
everything as GitHub Actions. After every push, the following commands
will run in an online environment:

1.  `python3.10` will be installed
2.  All the dependencies specified in `requirements.txt` will be
    installed
3.  Your grammar (located in `calc.g4` by default) will be used to parse
    each file in `tests/`
4.  Any personal code you place in the file `user.py` will run
5.  Any code you place in `run.py` will run

You can observe the outputs of these actions by going to the `Actions`
tab on GitHub and selecting your most recent commit.

Before your final submission, you will need to add code to `run.py` to
run all of your examples in your newly written language and output the
results.

# Assignment Specification

You are welcome to come up with your own syntax for your language. Do
you want lines to end with `;`? Or they could end with `!`… What order
are expressions and operators read in? How do you define a variable? All
these are up to you. I encourage you to make it your own, but also
remember that you will need to define the CFG to parse it!

## Language Requirements

You will construct a language with the following features:

1.  Handle integer, float, and boolean types
2.  Ability to perform arithmetic operations with full PEMDAS/BODMAS
    rules (including parentheses)
3.  Ability to perform basic boolean operations (and, or, xor, not)
4.  Convert numerical types into boolean using less-than, greater-than,
    or equals
5.  Raise errors:
    1.  Type error (arithmetic between boolean and non-boolean)
    2.  Division by 0
    3.  Variable referenced before assignment
6.  Ability to define and reference variables
7.  Ability to print values
8.  Ability to define simple functions of 2 variables

## Final submission

-   [ ] Write your interpretter as you see fit (lots of in-class
    guidance and activities will be available)
-   [ ] Add code to `run.py` to run your interpretter over a series of
    code examples which demonstrate each of the requirements above
-   [ ] Ensure that the output on Github Actions is easy to understand
-   [ ] Provide a writeup describing your language and its capabalities
    -   [ ] Justify any specific design decisions you made

## Updated instructions
The instructions will be updated with daily agendas as the class progresses.
You may refer to the latest version of the assignment at https://github.com/infiniterik/byol.
    
## Friday, September 16

By Friday you should be ready to describe your syntax. Write a few
examples of statements or expressions that demonstrate each of your
requirements and put them in text files. What is the extension for your
programming language?

Then, start working on your grammar. Create a `[language-name].g4` file.
Remember to test it out and make commits. Make sure you know how to
compile your grammar and test to make sure your expressions and
statements are approariately parsed.

The ANTLR plugin for VS-code is very useful for testing purposes. You
may also test by repeatedly pushing to GitHub.

> NOTE: Everytime you use antlr to regenerate your parser, it will
> overwrite the code in your folder. Remember to commit frequently so
> you don't lose anything!
