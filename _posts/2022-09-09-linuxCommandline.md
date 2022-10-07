---
layout: post
title: Linux Command Line
---

# Why the Command Line?!?!

- greater control of an OS or application;
- faster management of many operating systems;
- ability to store scripts to automate regular tasks

When a user first enters a command line, they fidn it challanging because it requires them memorising a banch of commands
along with thier options. However once a user gets to know how to navigate the command line, know it's structure they are 
bound to be more productive providing the user with control, greater speed, and abiity to automate tasks more easily though
scripting.

# Understanding the Command Line

**What is a Command Line?**<br>
You can call it a program that opens a window and lets you interact with the shell. 

                                    OR

A comand line is simply a text-based interface to the computer where you can type commands, manipulate files, execute programs, and open documents.

**Navigation**<br>
Like Windows, the files on a Linux system are arranged in what is called a hierarchical directory structure. This means that they are organized in a tree-like pattern of directories (called folders in other systems), which may contain files and subdirectories. The first directory in the file system is called the root directory which contains files and subdirectories, which contain more files and subdirectories......

At any given moment, we are located in a single directory. Inside that directory, we can see its files and the pathway to its parent directory and the pathways to the subdirectories of the directory in which we are standing called the working directory. To see the name of the working directory, we use  `pwd`(print working directory) command.

{image}

To change the current working directory we use the `cd` command. To do this, we type cd followed by the pathname of the desired working directory. A pathname is the route we take along the branches of the directory tree to get to the directory we want.


{image}