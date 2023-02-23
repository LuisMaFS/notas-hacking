
# Level 1 al 2

## Objetivo.

La contraseña para el siguiente nivel esta guardada en un archivo llamado **-** located en el home directory.

## Datos de acceso al nivel.

bandit1
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

## Solución.

bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$

## Notas opcionales.

-ls:  enumerar el contenido del directorio. 
-cat ./-: usar el comando cat - no devuelve nada. Entonces, en lugar de escribir solo cat -, agregamos la ruta y escribimos ./- 

## Referencias.

https://overthewire.org/wargames/bandit/bandit2.html
https://medium.com/@theGirlWhoEncrypts/overthewire-bandit-level-1-level-2-9da2e3f51fb