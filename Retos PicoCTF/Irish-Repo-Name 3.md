# Irish-Repo-Name 3

## Objetivo.

There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/29132/` ([link](https://jupiter.challenges.picoctf.org/problem/29132/)) or http://jupiter.challenges.picoctf.org:29132. Try to see if you can login as admin!

## Solución.

En el lado izquierdo de la pagina, esta un boton de menú, accedemos a la opción de "Admin Login"
Ahora solo tiene la parte de password, el usuario ha desaparecido.
E ingresamos concontraseña la inyección SQL **' or 1 == 1;**.

La página nos regresa la contraseña, codificada en ROT13. por lo que parece que ha sido cambiada.

Nos apoyaremos de CyberChef, para colocar la inyección SQL **' or 1 = = 1;** esta SQL cambia **be 1 = = 1;**

Y obtendremos la bandera
**picoCTF{3v3n_m0r3_SQL_06a9db19}**

## Notas opcionales.

ROT13 es un sencillo cifrado utilizado para ocultar un texto sustituyendo cada letra por la letra que está trece posiciones por delante en el alfabeto. A se convierte en N, B se convierte en O y así hasta la M, que se convierte en Z.

## Referencias.

https://latam.kaspersky.com/resource-center/definitions/sql-injection
https://www.youtube.com/watch?v=1o53Bwty1E4&ab_channel=hackadvisermx