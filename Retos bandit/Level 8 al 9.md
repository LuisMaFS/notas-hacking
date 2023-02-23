# Level 8 al 9

## Objetivo.

La contaseña para el siguiente nivel, está almacenada en el archivo **data.txt** is la única línea de texto que aparece una vez.

## Datos de acceso al nivel.

bandit8
TESKZC0XvTetK0S9xNwm25STk5iWrBvP

## Solución.

bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ sort data.txt | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## Notas opcionales.

uniq es un comando que filtra la entrada y escribe en la salida. En concreto, filtra en función de líneas idénticas. Tiene una bandera -u, que filtra por líneas únicas (líneas que aparecen solo unas). Otra funcionalidad interesante es, por ejemplo, que también puede count (-c) o solo devolver líneas duplicadas (-d).

El comando se usa a menudo con sort. Para que uniq filtre líneas únicas, las líneas deben ordenarse. sort ordena las líneas de un archivo de texto. Además, tiene banderas para ordenar a la reverse (-r) y ordenar numerically (-n).

## Referencias.

https://overthewire.org/wargames/bandit/bandit9.html
https://ryanstutorials.net/linuxtutorial/piping.php
https://mayadevbe.me/posts/overthewire/bandit/level9/