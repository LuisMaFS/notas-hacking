
# Level 7 al 8

## Objetivo.

La contraseña para el siguiente nivel está almacenada en el archivo **data.txt** al lado de la palabra  **millionth**

## Datos de acceso al nivel.

bandit7
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## Solución.

bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ du -b data.txt
4184396 data.txt
bandit7@bandit:~$ cat data.txt | grep millionth
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP


## Notas opcionales.

Por lo tanto, simplemente revisar el archivo llevaría demasiado tiempo y sería demasiado esfuerzo.
En su lugar, podemos intentar usar `grep`, ya que la contraseña está en la misma línea que la palabra 'millionth'

## Referencias.

https://overthewire.org/wargames/bandit/bandit8.html
https://mayadevbe.me/posts/overthewire/bandit/level8/