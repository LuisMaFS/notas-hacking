# Level 3 al 4

## Objetivo.

La contraseña para el siguiente nivel  está almacenada en un archivo oculto en el directorio **inhere**.

## Datos de acceso al nivel.

bnadit3
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

## Solución.

bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
bandit3@bandit:~/inhere$
## Notas opcionales.

Un archivo oculto en Linux comienza con .. El comando ls muestra solo archivos no ocultos. Sin embargo, con el indicador -a muestra todos los archivos, específicamente también los archivos ocultos.

## Referencias.

https://overthewire.org/wargames/bandit/bandit4.html
https://mayadevbe.me/posts/overthewire/bandit/level4/