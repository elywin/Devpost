---
layout: post
title: Deploying a Django Application using Heroku
---

**Deploying a Django application from Github using Heroku**<br>
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

> pip install django-heroku

**Note:** Check this [article](https://devcenter.heroku.com/articles/django-app-configuration) out to see why you need these pacakages 

4. Add a requirements.txt file

> pip freeze > requirements.txt

**Note:**Heroku will recognize a deployed application as a Python application only if it has a requirements.txt file in the root directory. Even if your application has no module dependencies, it should include an empty requirements.txt file to indicate that your app has no dependencies.

Your requirements.txt file should look like this:

```
asgiref==3.3.4
dj-database-url==0.5.0
Django==3.2
django-heroku==0.3.1
gunicorn==20.1.0
psycopg2==2.8.6
pytz==2021.1
sqlparse==0.4.1
whitenoise==5.2.0
```

5. Add the following import statement to the top of settings.py:

> import django_heroku

6. Then add the following to the bottom of settings.py to activate Django-Heroku.:

> django_heroku.settings(locals())

7. Then add the following in the settings.py‘s middleware section (at the top):

> 'whitenoise.middleware.WhiteNoiseMiddleware',

8. Create an account on [Heroku](https://id.heroku.com/login) if you havent already created one.

9. Create an app and give it a name, Choose any name for your app. Heroku will inform you if the name already exists or its free to use.

10. Add your app domain name to ALLOWED_HOSTS in settings.py, replace the "herokudjangoapp" with your app name.

> ALLOWED_HOSTS = ['herokudjangoapp.herokuapp.com']

11. Push your code to your github repository

12. On heroku navigate to your app and select the deploy method you prefer, for this case we shall use GitHub,
select github .

   1. connect your github account
   2. search for your repository with the django app and click connect
   3. Select the branch to deploy 
   4. Deploy the branch

**Note:**If you get an error message with collectstatic, simply disable it by instructing Heroku to ignore running the manage.py collecstatic command during the deployment process.

In your terminal run the folloowing command, replace herokuappname with the name of the app you created on heroku and Deploy branch again:

> heroku config:set DISABLE_COLLECTSTATIC=1 -a herokuappname

13. create super user to have access to the admin dashboard

Run the following command in your terminal, replace herokuappname with the name of the app you created on heroku:

> heroku run python manage.py createsuperuser -a herokuappname

You can still run the migration command in the terminal incase you dont add it to the procfile or make any changes to the models.

> heroku run python manage.py migrate -a herokuappname