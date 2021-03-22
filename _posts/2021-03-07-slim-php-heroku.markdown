---
layout: post
title:  "Slim Framework App PHP with deploy in Heroku"
date:   2021-03-07 20:07:28 -0300
categories: tutorial
---
Slim Framework PHP application with automatic deployment on Heroku.
==============================

## Introduction
The main objective of this repo is to be able to automatically deploy our PHP Slim Framework application on Heroku.

## 1- Forke project
As a first step, we forked this project from the button located at the top right of the repository page.

## 2- We upload our code
Once forked, we clone the repo with `git clone <repo url>` and add our PHP code (SLIM Framework) inside the `/app/` folder.
Then we commit and push the changes.

```sh
git add .
git commit -m "first commit"
git push -u origin main
```

## 3- Create and configure the App in Heroku

We go to the Heroku page https://heroku.com/, we log in if we have an account or create one.

When you log in, Heroku shows us your dashboard, here we will click on **New** and then on **Create new app**:

![Heroku1](https://i.ibb.co/MVTSH69/heroku1.png)

In this section we add the name of the app, select the United States region and then click the **Create app** button

![Heroku2](https://i.ibb.co/TwPJnrW/heroku2.png)

Now we go to the **Deploy** section and click on the GitHub option, which will show us our user or we will have to log in with GitHub. Then we look for the name of our repo and it will appear below:

![Heroku3](https://i.ibb.co/vZjZgD6/heroku3.png)

We select the repo and click on **Connect**

Once this is done, we choose the github branch that we want to deploy with our Heroku application, in our case `main`, and click **Enable Automatic Deploys**. In this way, every time a modification is made to this branch, Heroku will automatically update the application.

![Heroku4](https://i.ibb.co/d0z1NWv/heroku4.png)

The last thing we should do is click the **Deploy Branch** button. This is only done once, then it will be done automatically.

![Heroku5](https://i.ibb.co/sVYwVZx/heroku5.png)

We can check from GitHub if the deployment was done successfully.

![Heroku6](https://i.ibb.co/K95j3fp/heroku6.png)

From the button **View deployment** we access the URL of the deployed app.

https://slim-php-heroku.herokuapp.com/

Enjoy!

### 2021