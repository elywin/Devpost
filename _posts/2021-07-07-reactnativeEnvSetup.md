---
layout: post
title: React-Native Environment setup(Ubuntu)
---

**How to Install and Setup React Native on Ubuntu**<br>
Hello, In this article, We will learn how to install and setup React Native on Ubuntu.

These are the steps we will be following:

1. Install Node.JS and npm
2. Install React Native Command Line (CLI)
3. Install Java Development Kit
4. Setup Android development environment
5. Creating a Sample application
6. Preparing Android Device (physical or virtual device)
7. Run React Native App

Now that the steps are layed out, lets begin the setup.

1. Install Node.JS and npm

Let’s move to terminal.

Update apt package manager

> sudo apt update 

Install nodejs using apt package manager.

> sudo apt install nodejs

Verify nodejs installation

> nodejs --version


Install npm

> sudo apt install npm

Verify npm installation

> npm --version

2. Install React Native Command Line (CLI)

> npm install -g react-native-cli

**NB:** If you get an error like Cannot find module ‘npmlog’ you can install npm directly using this command. `If the above command run successfully then no need to run this command`.

> curl -0 -L https://npmjs.org/install.sh | sudo sh

