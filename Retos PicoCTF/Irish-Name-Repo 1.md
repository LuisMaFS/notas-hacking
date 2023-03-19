# Irish-Name-Repo 1

## Objetivo.

There is a website running at `https://jupiter.challenges.picoctf.org/problem/39720/` ([link](https://jupiter.challenges.picoctf.org/problem/39720/)) or http://jupiter.challenges.picoctf.org:39720. Do you think you can log us in? Try to see if you can login!

## Solución.

En el lado izquierdo de la pagina, esta un boton de menú, accedemos a la opción de "login"
E ingresamos como usuario **admin** y contraseña **password**.

La página nos dice que en ingreso es incorrecto. Por lo que revusamos el código fuente. Y podemos notar la siguiente línea.
**input type="hidden" name="debug" value="0"**
Ese valor lo cabiamos a 1 y volvemos a logearnos a la página.

Seguimos sin ingresar y nos dice una pista del fallo.
**username: admin**
**password: password**
**SQL query: SELECT * FROM users WHERE name='admin' AND password='password'**

Esta es la consulta SQL para que la base de datos válide el inicio de sesión.

Para iniciar sesión, hacemos la siguiente inyección SQL.
**'or 1 = = 1;**
Volvemos a loggear y obtendremos la bandera
**picoCTF{s0m3_SQL_c218b685}**

## Notas opcionales.

Una inyección de SQL, a veces abreviada como SQLi, es un tipo de vulnerabilidad en la que un atacante usa un trozo de código SQL (lenguaje de consulta estructurado) para manipular una base de datos y acceder a información potencialmente valiosa. Es uno de los tipos de ataques más frecuentes y amenazadores, ya que puede atacar prácticamente cualquier sitio o aplicación web que use una base de datos basada en SQL (la mayoría).

## Referencias.

https://latam.kaspersky.com/resource-center/definitions/sql-injection
https://www.youtube.com/watch?v=0EDbUSDqrng&t=193s&ab_channel=hackadvisermx