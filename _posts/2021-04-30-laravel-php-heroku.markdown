---
layout: post
title:  "Laravel Framework PHP with deploy in Heroku"
date:   2021-04-30 19:10:51 -0300
categories: tutorial
---
Laravel Framework PHP application with automatic deployment to Heroku.
===============================

## Introduction
The main objective of this repo is to be able to automatically deploy our PHP Laravel Framework application on Heroku.

## 1- Fork project
As a first step, we forked this project from the button located at the top right of the repository page.

## 2- We upload our code
Once forked, we clone the repo with `git clone <repo url>` and add our code into the Laravel project.
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

![Heroku4](https://i.ibb.co/0Z1Psrx/heroku8.png)

Then we should click on the **Deploy Branch** button. This is only done once, then it will be done automatically.

![Heroku5](https://i.ibb.co/sVYwVZx/heroku5.png)

Now we go inside the Heroku dashboard to the **More** > **Run console** option

![Heroku11](https://i.ibb.co/Htvyp0x/11.png)

We execute the following command to obtain the APP KEY that we will need for the application to run.

`php artisan key:generate --show`

![Heroku12](https://i.ibb.co/zJpkKDT/12.png)

The console will return a hashed string similar to `ZEqur46KTEG91iWPhKGY42wtwi3rtkx2`

![Heroku14](https://i.ibb.co/93f688g/13.png)

We copy that value and go to the **Settings** tab and then to the **Config Vars** section and add 2 variables:

`APP_DEBUG: true`

`APP_KEY: ZEqur46KTEG91iWPhKGY42wtwi3rtkx2`

![Heroku13](https://i.ibb.co/cxmyR1q/10.png)

We can check from GitHub if the deployment was successful.

![Heroku6](https://i.ibb.co/RQzHTzp/9.png)

From the **View deployment** button we access the URL of the deployed app.

https://laravel-php-heroku.herokuapp.com/

Enjoy!

### 2021
