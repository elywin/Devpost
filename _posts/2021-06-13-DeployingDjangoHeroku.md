---
layout: post
title: Deploying a Django Application using Heroku
---

**Deploying a Django application using Heroku**<br>
Before deploying the app we, we need to add a few configuration files and install some packages to run our app in the production environment.

1. Add a Procfile in the project root directory to define process types and explicitly declare what command should be executed to start your app.

> touch Procfile


Open the Procfile and add the line below.

> web: gunicorn djangoherokuapp.wsgi

**Note:**Change djangoherokuapp to the name of your project to point to the location of the wsgi.py file.

Add the following line to the procfile too.

> release: python manage.py migrate

This line will migrate your database on heroku

2. Add a runtime.txt file in the project root directory.

>touch runtime.txt

In the runtime.txt file add the following line specifying the correct Python version in regards to your django app environment.

> python-3.9.2

3. Install the following packages in the environment

> pip install gunicorn dj-database-url whitenoise

> pip install psycopg2-binary

**Note** Check this [article](https://devcenter.heroku.com/articles/django-app-configuration) out to see why you need these pacakages 


