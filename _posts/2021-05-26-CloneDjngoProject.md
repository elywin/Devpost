---
layout: post
title: Cloning a Django Project
---
**How To Clone and Setup a Django Project On Linux**

**Step 1**<br>
Clone The Project [repository](https://techcrunch.com/2012/07/14/what-exactly-is-github-anyway/).

> git clone https://github.com/username/projectname.git

**Step 2**<br>
Move into the cloned Project Directory.

> cd projectname

**Step 3**<br>
Create a Virtual Environment called `env`.

> python3 -m venv env

**Step 3**<br>
Activate the Virtual Environment.

> source env/bin/activate

You will know the virtual environment is activated once the prefix is changed to (env), which will look similar to the following depending on what directory you are in:

**from:**<br>
> elywin@elywin:~/projects/blog$ 

**to**<br>
> `(env)`elywin@elywin:~/projects/blog$ 


**Step 4**<br>
Install Requirements Package, this will install the project dependecies.

> pip install -r requirements.txt

**Step 5**<br>
Migrate Database.

> python manage.py migrate

**Step 6**<br>
Create Super User that will access the database admin side.

> python manage.py createsuperuser

**Step 2**<br>
Finally Run The Project. 

> python manage.py runserver

Navigate to the link below in the browser to see the output:

> http://127.0.0.1:8000/
