# Level 10 al 11

## Objetivo.

La contraseña para el siguiente nivel está almacenada en el archivo  data.txt, el cual contiene datos codificados en base 64.

## Datos de acceso al nivel.

bandit10
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## Solución.

bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ base64 -d data.txt
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Notas opcionales.

Linux tiene un comando llamado base64 que permite codificar y decodificar en base 64. Para decodificar, necesitamos usar la bandera -d.

## Referencias.

https://overthewire.org/wargames/bandit/bandit11.html
https://mayadevbe.me/posts/overthewire/bandit/level11/
