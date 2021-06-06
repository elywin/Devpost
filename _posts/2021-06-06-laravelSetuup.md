---
layout: post
title: Cloning a laravel project
---
**How to Setup a Laravel Project You Cloned from Github or Gitlab**<br>
Lets take a scenario where you find a Laravel project off Github or Gitlab and you want to use it locally, learn from it or contribute to it, this is what you need to do.

Obejectives:<br>
1. Clone the repository
2. Branch off the main branch
3. Install cmposer dependencies
4. Create a copy of your .env file
5. Generate an app encryption key
6. Create database for the application
7. In the .env file, add database information 
8. Migrate the database
9. Seed the database

**Step 1 - Clone the repository**

We can use git on your local computer to clone it from github or gitlab onto your local computer in a folder location of your choice. 
Note: Make sure you have git installed locally on your computer first.

> git clone link_to_repository


**Step 2 - Branch off the main branch**

You will need to be inside that project folder to branch off. So change directory to enter the cloned project folder.
 
> cd project_folder

Then branch off:

> git checkout -b new_branch_name

**Step 3 - Install Composer Dependencies**

Whenever you clone a new Laravel project you must now install all of the project dependencies.

> composer install

**Note:** If you run into any errors during the install process. Run: 

> composer update

or

> php composer.phar update

**Step 4 - Create a copy of your .env file**

We will make a copy of the .env.example file and create a .env file that we will edit inorder to configure the database.

> cp .env.example   .env

**Step 5 - Generate an app encryption key**

Laravel requires you to have an app encryption key which is randomly generated and stored in your .env file. The app will use this encryption key to encode  application cookies and password hashes.

> php artisan key:generate

If you check the .env file again, you will see a long random string of characters in the APP_KEY field. If you dont see the string then use the second command below to get the string, copy it and paste it in the .env file where
`APP_KEY=;`

or 

> php artisan key:generate –show

**Step 6 - Create a database for your project.**

**Step 7 - In the .env file, add database information**
 
To allow Laravel to connect to the database that you just created in the previous step, we must add the connection credentials in the .env file to match the credentials of the database you just created. This will allow us to run migrations and seed the database.

```
DB_HOST=localhost 
DB_PORT=3306
DB_DATABASE=your_database_name
DB_USERNAME=your_username
DB_PASSWORD=your_userpassword
```

Depending on your application, you might need to make some changes to your app.php file in the config folder such as the timezone. If you do make any changes be sure to flush the cache.

```
 php artisan optimize:clear
 php artisan config:clear
 php artisan cache:clear
 php artisan config:cache
```

**Step 8 - Migrate the database**

Once your credentials are in the .env file, now you can migrate your database.

> php artisan migrate

**Note:**check your database to see the if all was migrated as expected.

**Step 9 - Seed the database**

If your project has the seeding file setup then, seeding will fill your database with dummy data.

After the migrations are complete and you have the database structure required, then you can seed the database

> php artisan db:seed

You may use the --class option to specify a specific seeder class to run individually:
 
> php artisan db:seed –class=UsersTableSeeder

This will fill only the specified table in the database. Check your database to confirm the if the data has been inserted successfully.

Conclusion<br>
That is all you need to get started on a standard laravel project. Be sure to read the readme.md file on github or gitlab before you start customizing a project. This will often contain specific steps that are unique to that project.
