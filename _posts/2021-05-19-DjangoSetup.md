---
layout: post
title: Django Setup
---
**Django Environment & Project Setup**<br>
Django is a free and open-source web framework written in Python that adheres to the model template view (MTV) software architectural pattern, its core principles being scalability, re-usability and rapid development.  

The `model` is the single definitive source of your data.
The `view` describes the data that gets represented to the user via a Python callback function to a specific URL.
The `template` is how Django generates HTML dynamically.

To set up a Django development environment, We are going to install `Python 3`, `pip 3`, `Django` and `virtualenv` in order to equip you with the tools necessary for developing web applications with Django.

**Step 1 — Setting Up Python 3**

> $ sudo apt update<br>
> $ sudo apt -y upgrade

Once everything is updated, we can install Python 3:

> sudo apt-get install python3

To verify the successful installation of Python 3, run a version check:

> python3 -V


