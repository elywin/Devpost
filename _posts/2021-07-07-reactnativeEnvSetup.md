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

**Install Node.JS and npm**

Let’s move to terminal.

**Update apt package manager**

> sudo apt update 

**Install nodejs using apt package manager.**

> sudo apt install nodejs

**Verify nodejs installation**

> nodejs --version

**Install npm**

> sudo apt install npm

**Verify npm installation**

> npm --version

There are two ways we can set up our mobile application:<br>
1. Using ReactNative Command Line 
2. Expo Command Line

# 1.Using ReactNative CLI

**Install React Native Command Line (CLI)**

> npm install -g react-native-cli

**NB:**   If you get an error like Cannot find module ‘npmlog’ you can install npm directly using this command. `If the above command run successfully then no need to run this command`.

> curl -0 -L https://npmjs.org/install.sh \| sudo sh

**Install Java Development Kit**

First, We have to add Oracle’s Personal Package Archives(PPA)

> sudo add-apt-repository ppa:webupd8team/java

**Update your package repository.**

> sudo apt update

Install Oracle JDK 1.8(stable) atleast, recommended version for React Native Development but You can install multiple Java Installations in one machine. Java is already installed on the Ubuntu 20.04 system. Therefore, we do not need to install it on this system again.

> sudo apt install oracle-java8-installer

We will need to set Java 1.8 as default.

> sudo apt install oracle-java8-set-default

**Verify java installation**

> javac --version

**Setup Android development environment**

**Install AndroidStudio**

[Download and install Android Studio](https://developer.android.com/studio). While on Android Studio installation wizard, make sure the boxes next to all of the following items are checked:

- Android SDK
- Android SDK Platform
- Android Virtual Device

Then, click "Next" to install all of these components.

Once setup has finalized and you're presented with the Welcome screen, proceed to the next step.

**Install the Android SDK**

To do that, open Android Studio, click on "Configure" button and select `SDK Manager`.

> **NB:**  The SDK Manager can also be found within the Android Studio "Preferences" dialog, under Appearance & Behavior → System Settings → Android SDK.

Select the "SDK Platforms" tab from within the SDK Manager, then check the box next to "Show Package Details" in the bottom right corner. Look for and expand the Android 10 (Q) entry, then make sure the following items are checked:

- Android SDK Platform 29
- Intel x86 Atom_64 System Image or Google APIs Intel x86 Atom System Image

Next, select the "SDK Tools" tab and check the box next to "Show Package Details" here as well. Look for and expand the "Android SDK Build-Tools" entry, then make sure that 29.0.2 is selected.

Finally, click "Apply" to download and install the Android SDK and related build tools.

**Configure the ANDROID_HOME environment variable**

React Native tools require some environment variables to be set up in order to build apps with native code.

Add the following lines to your `$HOME/.bash_profile` or `$HOME/.bashrc` (if you are using `zsh` then `~/.zprofile` or `~/.zshrc`) config file:

Go to terminal and run command

> $HOME/.bash_profile 

**NB:**  Make sure you use the correct Android SDK path. You can find the actual location of the SDK in the Android Studio "Preferences" dialog, under Appearance & Behavior → System Settings → Android SDK.


When the file opens add the following lines:
```
export ANDROID_HOME=$HOME/Android/Sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
```
 **NB:**  If you not able to edit this file you can run these command in terminal.

**Verify that ANDROID_HOME has been set by running:**

> echo $ANDROID_HOME 

And verify that the appropriate directories have been added to your path by running:

> echo $PATH.

**Creating a Sample application**

> react-native init SampleProject

**Preparing Android Device for development**

You will need an Android device to run your ReactNative App. It can be either a physical or virtual Android device.

**Using a Virtual Device (emulator)**

To do that open the android studio and create a virtual device . and power up AVD(Android Virtual Device). If you have recently installed Android Studio, you will likely need to create a new AVD(Android Virtual Device). Select `Create Virtual Device`, then pick any Phone from the list and click "Next", then select the Q API Level 29 image.

Click "Next" then "Finish" to create your AVD. At this point you should be able to click on the green triangle button next to your AVD(Android Virtual Device) to launch it, then proceed to the next step.

**Using a physical device**

If you have a physical Android device, you can use it for development in place of an AVD by plugging it in to your computer using a USB cable. Following the instructions: [how to setup physical android device for development](https://reactnative.dev/docs/running-on-device).

**Run React Native App**

**Move into the project folder**

> cd SampleProject

**Start Metro**

> react-native start

**Open a new terminal tab and run the application.**

> react-native run-android

If everything is set up correctly, you should see your new app running on your Android device.

# 2.Using Expo CLI

Assuming that you have Node installed, you can use npm to install the Expo CLI command line utility:

**install the Expo CLI**

> npm install -g expo-cli

**Create a new React Native project**

> expo init DemoProject

**Move into the project folder/directory**

> cd DemoProject

**Run the project**

> expo start

The development server will be started for you.

**Running the app on a device ios or android**

Install the [Expo](https://docs.expo.io/) client app on your iOS or Android phone and connect to the same wireless network as your computer.

- On Android, use the Expo app to scan the QR code from your terminal to open your project.
- On iOS, use the built-in QR code scanner of the Camera app.

If everything is set up correctly, you should see your new app running on your device.
