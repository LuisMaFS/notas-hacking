# Level 2 al 3

## Objetivo.

La contraseña para el siguiente nivel es almacenada en  un archivo llamado **spaces in this filename** localizado en el home directory.

## Datos de acceso al nivel.

bandit2
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

## Solución.

bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat spaces\ in\ this \ filename 
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$

## Notas opcionales.

Ej el nombre del archivo tiene múltiples espacios. Por lo tanto, para leer el archivo, tenemos que colocar una barra invertida para escapar de un espacio.

## Referencias.

https://overthewire.org/wargames/bandit/bandit3.html
https://mayadevbe.me/posts/overthewire/bandit/level3/
