# Irish-Name-Repo 2

## Objetivo.

There is a website running at `https://jupiter.challenges.picoctf.org/problem/52849/` ([link](https://jupiter.challenges.picoctf.org/problem/52849/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:52849

## Solución.

En el lado izquierdo de la pagina, esta un boton de menú, accedemos a la opción de "Admin Login"
E ingresamos como usuario **admin** y contraseña la inyección SQL **' or 1 == 1;**.

La página nos dice que en ingreso es incorrecto. Porque ha detectado la inyección SQL

Pero si agregamos la inyección SQL.
usuario **admin';** y contraseña **password**.
Con esto hacemos que el quaery despues de la comilla que cierra sea ignorado y podemos ingresar.

Y obtendremos la bandera
**picoCTF{m0R3_SQL_plz_fa983901}**

## Notas opcionales.

Una inyección de SQL, a veces abreviada como SQLi, es un tipo de vulnerabilidad en la que un atacante usa un trozo de código SQL (lenguaje de consulta estructurado) para manipular una base de datos y acceder a información potencialmente valiosa. Es uno de los tipos de ataques más frecuentes y amenazadores, ya que puede atacar prácticamente cualquier sitio o aplicación web que use una base de datos basada en SQL (la mayoría).

## Referencias.

https://latam.kaspersky.com/resource-center/definitions/sql-injection
https://www.youtube.com/watch?v=1o53Bwty1E4&ab_channel=hackadvisermx