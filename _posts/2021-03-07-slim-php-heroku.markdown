---
layout: post
title:  "Slim Framework App PHP with deploy in Heroku"
date:   2021-03-07 20:07:28 -0300
categories: tutorial
---
Aplicación Slim Framework PHP con despliegue automático en Heroku.
==============================

## Introducción
El principal objetivo de este repo es poder desplegar de forma automática nuestra aplicación PHP Slim Framework en Heroku.

## 1- Forkear proyecto
Como primer paso, forkeamos este proyecto desde el boton ubicado en la parte superior derecha de la pagina del repositorio.

## 2- Subimos nuestro codigo
Una vez forkeado, clonamos el repo con `git clone <url del repo>` y agregamos nuestro codigo PHP (SLIM Framework) dentro de la carpeta `/app/`.
Luego comiteamos y pusheamos los cambios.

```sh
git add .
git commit -m "first commit"
git push -u origin main
```

## 3- Crear y configurar la App en Heroku

Nos dirigimos a la página de Heroku https://heroku.com/, iniciamos sesión si tenemos cuenta o creamos una.

Heroku al iniciar sesión nos muestra su dashboard, aquí haremos clic en **New** y luego en **Create new app**:

![Heroku1](https://i.ibb.co/MVTSH69/heroku1.png)

En esta sección agregamos el nombre de la app, seleccionamos la región United States y luego clic en botón **Create app**

![Heroku2](https://i.ibb.co/TwPJnrW/heroku2.png)

Ahora vamos a la sección **Deploy** y hacemos clic en la opción de GitHub, la cual nos mostrará nuestro usuario o tendremos que iniciar sesión con GitHub. Después   buscamos el nombre de nuestro repo y aparecerá abajo:

![Heroku3](https://i.ibb.co/vZjZgD6/heroku3.png)

Seleccionamos el repo y hacemos clic en **Connect**

Una vez hecho esto, elegimos la rama de github que queremos deplegar con nuestra aplicación Heroku, en nuestro caso `main`, y hacemos clic en **Enable Automatic Deploys**. De esta forma, cada vez que se haga una modificación a esta rama, Heroku va actualizar automáticamente la aplicación.

![Heroku4](https://i.ibb.co/d0z1NWv/heroku4.png)

Lo utlimo que deberiamos hacer es clic en el botón **Deploy Branch**. Esto solo se hace una sola vez, luego se hará de forma automática.

![Heroku5](https://i.ibb.co/sVYwVZx/heroku5.png)

Podemos verificar desde GitHub si el depliegue se hizo con exito.

![Heroku6](https://i.ibb.co/K95j3fp/heroku6.png)

Desde el botón **View deployment** accedemos a la URL de la app desplegada.

https://slim-php-heroku.herokuapp.com/


### 2021 - UTN FRA