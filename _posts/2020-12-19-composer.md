---
layout: post
title: Composer PHP dependency manager
---
**What is composer?<br>**
Composer is a dependency management tool for PHP. It allows you to declare the libraries your project depends on and manages them for you (installing or updating).

**Why should you use composer?**<br>
If you have been using vanilla php for a while you find that you **recreate** the same tpe of functionality over and over again such as user authentication, application  routing, database management and not forgetting the helper classes and functions. wouldn`t it be better or more convenient to create this functionality once and **re-use** it in multiple projects?

You probably thinking "i can just copy over a file or line of code", but what if the environment changes or the codebase(source code) is different? You will have to rewrite code in-order to make it work with the new app.

Imagine you had a way of managing all your code and dependencies, then re-using your code on a new project would be much easier and convenient. And thats exactly why you need composer.

**How do you install composer?**<br>
**Linux / MacOS installation**

> `Composer requires PHP 5.3.2+ to run`.

1. Download Composer from the official website using the following command:<br>

```
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
```

2. Verify the installer’s signature (SHA-384) to ensure that the installer file is not corrupt. using the following command:<br>

```
 php -r "if (hash_file('sha384', 'composer-setup.php') === 'e0012edf3e80b6978849f5eff0d4b4e4c79ff1609dd1e613307e16318854d24ae64f26d17af3ef0bf7cfb710ca74755a') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
 ```

Now you can install composer `locally` or `globally`. Local installation means that the dependency manager will be stored in your current working directory, and you have to specify the path before executing corresponding commands. Meanwhile, global installation allows you to run Composer from anywhere on your system.

- Local installation
> php composer-setup.php

- Global installation
```
php composer-setup.php --install-dir=/usr/local/bin --filename=composer
```

If all the commands are issued correctly then you will see a message smilar to this:
```
All settings correct for using Composer
Downloading...
Composer (version 1.10.5) successfully installed to: /usr/local/bin/composer
```

3. After the installation is complete remove the installer:
> php -r "unlink('composer-setup.php');"

4. Test the Composer installation by running the command:
> composer

The command line will display composer version:
```
______
  / ____/___ ____ ___ ____ ____ ________ _____
 / / / __ / __ `__ / __ / __ / ___/ _ / ___/
/ /___/ /_/ / / / / / / /_/ / /_/ (__ ) __/ /
____/____/_/ /_/ /_/ .___/____/____/___/_/
                  /_/

Composer version 1.10.5 2020-02-12 16:20:11
```

**How do you use composer?**<br>
There are two files that control project dependencies: `composer.json` and `composer.lock`,though the most important one is composer.json. 
You can create the composer.json file manually or directly call composer to require a dependency and the file will be created.

> composer.json file contains dependencies or packages that are downloaded or required to be downloaded, it also checks for version compatibility with your project. If you are using an older package, composer.json will let you know in order to avoid issues with the project.

There are two ways to install libraries with Composer:
- Using install command
- Using require command

1. Install command<br>
To use the `install` command, you need to create a composer.json file in your project first. In the composer.json file, you just need to declare the package or dependency. Lets use phpmailer library:

```
{
    "require": {
        "phpmailer/phpmailer": "~6.1"
    }
}
```

After adding the dependecy specifications, run the `composer install` command in the project directory. Composer installs the phpmailer package and its dependencies in the vendor directory. It also creates the composer.lock file which maintains a list of all of the packages and their exact installed versions.

2.Require command<br>
The composer require command is a sort of shortcut for creating a composer.json file and installing the package/dependency. require will create and add the specified package to your composer.json file automatically, it also updates the composer.lock file with the package and it`s exact installed version.

How to install the phpmailer package with the help of `require` command.<br> 
Run the following command in the project directory:

> composer require phpmailer/phpmailer

**How do you update composer dependencies?**<br>
In order to get the latest versions of the dependencies and to update the composer.lock file, you should use the update command:

>php composer.phar update

This command will resolve all dependencies of the project and write the exact versions of the dependencies into composer.lock.

If you only want to update a few packages or one package and not all, you specify the package names :

Updates a single package

```
php composer.phar update vendor/package-name 
```

Updates two packages specified

```
php composer.phar update vendor/package-name vendor/package-name2
```

If you only want to update a single package(s) to a specific version:

```
php composer.phar update vendor/package-name:2.0.1 vendor/package-name2:3.0.*
```

If you want to downgrade a package to a specific version without changing your composer.json file, you can use `--with` and provide a custom version:

```
php composer.phar update --with vendor/package:2.0.1
```

**Where do the packages/dependecies come from for you to use in your project?**<br>
The packages you use in your projects are imported from a composer package repository, `Packagist`. It lets you find packages and lets Composer know where to get the code from. 


>You can find the packagist.org source on:[Github](https://github.com/composer/packagist).
