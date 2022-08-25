---
layout: post
title:  "Slim Framework App PHP and MySQL DB with deploy in Heroku"
date:   2021-04-08 18:15:52 -0300
categories: tutorial
---
Slim Framework 4 PHP application with automatic deployment on Heroku.
===============================

## Introduction
The main objective of this repo is to be able to automatically deploy our PHP Slim Framework 4 application on Heroku.

## 1- Fork project
As a first step, we forked this project from the button located at the top right of the repository page.

## 2- We upload our code (optional if you add code)
Once forked, we clone the repo with `git clone <repo url>` and add our PHP code (SLIM Framework) inside the `/app/` folder.
Then we commit and push the changes.

```sh
git add .
git commit -m "first commit"
git push -u origin main
```

## 3- Create and configure the App in Heroku

We go to the Heroku page https://heroku.com/, log in if we have an account or create one.

Heroku when logging in shows us its dashboard, here we will click on **New** and then on **Create new app**:

![Heroku1](https://i.ibb.co/MVTSH69/heroku1.png)

In this section we add the name of the app, select the United States region and then click on the button **Create app**

![Heroku2](https://i.ibb.co/TwPJnrW/heroku2.png)

Now we go to the **Deploy** section and click on the GitHub option, which will show us our user or we will have to log in with GitHub. Then we look for the name of our repo and it will appear below:

![Heroku3](https://i.ibb.co/vZjZgD6/heroku3.png)

We select the repo and click on **Connect**

Once this is done, we choose the github branch we want to deploy with our Heroku app, in our case `main`, and click **Enable Automatic Deploys**. In this way, every time a modification is made to this branch, Heroku will automatically update the application.

![Heroku4](https://i.ibb.co/d0z1NWv/heroku4.png)

The last thing we should do is click the **Deploy Branch** button. This is only done once, then it will be done automatically.

![Heroku5](https://i.ibb.co/sVYwVZx/heroku5.png)

We can check from GitHub if the deployment was successful.

https://github.com/flippiJS/slim-php-mysql-heroku/deployments

![Heroku6](https://i.ibb.co/M87vVmd/Screenshot-at-Mar-29-19-44-49.png)

From the **View deployment** button we access the URL of the deployed app.

https://slim-php-mysql-heroku.herokuapp.com/

## 4- Create and configure the MySQL database (RemoteMysql)

For this we are going to create an account in RemoteMysql -> https://remotemysql.com/login.php that allows us free access to a MySQL server in the cloud.

In the **Create Account** part we complete the data and create the account:

![mysql1](https://i.ibb.co/rbZ7VXw/Screenshot-at-Mar-29-19-41-04.png)

We validate the account from the link sent to the email.

We log in, go to **DATABASES** and then **CREATE NEW DATABASE**

![mysql2](https://i.ibb.co/NSmB9Qh/Screenshot-at-Mar-29-19-49-44.png)

Once created, we will see the connection data to the database, it is **VERY IMPORTANT** to copy that information because it will only appear once.

![mysql3](https://i.ibb.co/YbcqDvK/Screenshot-at-Mar-29-19-50-39.png)

We copy this data and go to the Heroku project dashboard, in the **Settings** tab, the **Config Vars** option.

We add the following data Key -> Value:

```sh
MYSQL_HOST=remotemysql.com ("Server" field of the data we saved when creating the database in remotemysql.com)
MYSQL_PORT=3306 ("Port" field of the data we saved when creating the database in remotemysql.com)
MYSQL_USER=elcNx8VTCx ("Username" field of the data we saved when creating the database in remotemysql.com)
MYSQL_PASS=1234 ("Password" field of the data we saved when creating the database in remotemysql.com)
MYSQL_DB=elcNx8VTCx ("Database Name" field of the data we saved when creating the database in remotemysql.com)
```

![mysql3-1](https://i.ibb.co/8XQP54F/Screenshot-at-Mar-29-20-11-25.png)


## Access phpMyAdmin, remote database management

From the options of the created database, we access **phpMyAdmin**

![mysql4](https://i.ibb.co/jvrdKFm/Screenshot-at-Mar-29-19-51-39.png)

We start session with the data of the base

![mysql5](https://i.ibb.co/gF2nN9g/Screenshot-at-Mar-29-19-52-39.png)

From the panel of this site we will be able to manage the different databases, create and delete tables and make SQL queries.

![mysql6](https://i.ibb.co/4sY1XNF/Screenshot-at-Mar-29-19-53-10.png)


## Requirements to run locally

- Install PHP or XAMPP (https://www.php.net/downloads.php or https://www.apachefriends.org/es/download.html)
- Install Composer from https://getcomposer.org/download/ or via CLI:

```sh
php -r "copy('//getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('SHA384', 'composer-setup.php') === 'e115a8dc7871f15d853148a7fbac7da27d6c0030b848d9b3dc09e2a0388afed865e6a3d6b3c0fad45c48e2b5fc1196ae') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup. php'); } echo PHP_EOL;"
php composer-setup.php
```

## Run locally via XAMPP

- Copy project inside htdocs folder

```sh
C:\xampp\htdocs\
```
- Access the project folder by command line and then install Slim framework via Compose

```sh
cd C:\xampp\htdocs\<path-to-cloned-repo>
composer update
```
- In the index.php file add the following line below `AppFactory::create();`

```sh
// Set base path
$app->setBasePath('/app');
```
- Open from http://localhost/app or http://localhost:8080/app (depends on the port configured in the XAMPP panel)

## Run locally via PHP

- Access the project folder by command line and then install Slim framework via Compose

```sh
cd C:\<path-to-cloned-repo>
composer update
php -S localhost:666 -t app
```

- Open from http://localhost:666/

## .env file locally

Create inside the `/app/` folder the `.env` file taking reference to `.env.example`

We add the following data Key -> Value:

```sh
MYSQL_HOST=remotemysql.com ("Server" field of the data we saved when creating the database in remotemysql.com)
MYSQL_PORT=3306 ("Port" field of the data we saved when creating the database in remotemysql.com)
MYSQL_USER=elcNx8VTCx ("Username" field of the data we saved when creating the database in remotemysql.com)
MYSQL_PASS=1234 ("Password" field of the data we saved when creating the database in remotemysql.com)
MYSQL_DB=elcNx8VTCx ("Database Name" field of the data we saved when creating the database in remotemysql.com)
```

Enjoy!

### 2021
