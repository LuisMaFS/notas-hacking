# Logon

## Objetivo.

The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/44573`

## Solución.

Ingresar al link.
La página muestra un inicio de sesión, en mi caso ingrese con el usuario admin y como contraseña admin también.
El inicio de sesión fue correcto, pero dice que no hay bandera, por lo que usaremos una herramienta llamada cookie editor. Para cambiar el valor False a True del usuario Admin, refrescamos la página y obtenemos la bandera.

picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}

## Notas opcionales.

Cookie-Editor es una extensión del navegador enfocada en la productividad que le ayuda a administrar sus cookies con la menor cantidad de clics posible. Puede acceder a la lista de todas las cookies en la página actual, crear o modificar una cookie existente y eliminar una cookie en un máximo de tres clics. Cookie-Editor también le brinda la opción de importar cookies o exportarlas directamente a su portapapeles para compartirlas o guardarlas fácilmente.

## Referencias.

https://www.youtube.com/watch?v=JZc8R0VAmKE&ab_channel=secright
https://cookie-editor.cgagnier.ca/