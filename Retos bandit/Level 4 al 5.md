# Level 4 al 5

## Objetivo.

La contrasela para el siguiente nivel está almacenada en un archivo solo legible por humanos en el directorio **inhere** . Tip: isi tu terminal se perdió, intenta con el comando “reset”.

## Datos de acceso al nivel.

bandit4
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

## Solución.

bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat ./-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

## Notas opcionales.

Podemos ver que hay diez archivos.

Podemos usar diferentes métodos para encontrar el archivo legible por humanos y, por lo tanto, la contraseña.

Podríamos simplemente imprimir el contenido de cada archivo (cat). Esto, sin embargo, no es muy eficiente cuando tratamos con más archivos.

Podemos ver que solo '-file07' es de tipo 'ASCII text', que es una de las codificaciones que los humanos pueden leer. 

## Referencias.

https://overthewire.org/wargames/bandit/bandit5.html
https://mayadevbe.me/posts/overthewire/bandit/level5/