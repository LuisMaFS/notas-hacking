# Level 5 al 6

## Objetivo.

La contraseña para el siguiente nivel está  almacenada en un archivo en algún lugar debajo del directorio **inhere** y tiene todas las siguientes propiedades:

-   legible para humanos
-   1033 bytes de tamaño   
-   no ejecutable

## Datos de acceso al nivel.

bandit5
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

## Solución.

bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ ls -la
total 88
drwxr-x--- 22 root bandit5 4096 Jan 11 19:19 .
drwxr-xr-x  3 root root    4096 Jan 11 19:19 ..
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere00
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere01
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere02
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere03
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere04
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere05
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere06
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere07
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere08
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere09
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere10
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere11
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere12
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere13
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere14
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere15
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere16
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere17
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere18
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 maybehere19
bandit5@bandit:~/inhere$ ls -la maybehere00
total 72
drwxr-x---  2 root bandit5 4096 Jan 11 19:19 .
drwxr-x--- 22 root bandit5 4096 Jan 11 19:19 ..
-rwxr-x---  1 root bandit5 1039 Jan 11 19:19 -file1
-rwxr-x---  1 root bandit5  551 Jan 11 19:19 .file1
-rw-r-----  1 root bandit5 9388 Jan 11 19:19 -file2
-rw-r-----  1 root bandit5 7836 Jan 11 19:19 .file2
-rwxr-x---  1 root bandit5 7378 Jan 11 19:19 -file3
-rwxr-x---  1 root bandit5 4802 Jan 11 19:19 .file3
-rwxr-x---  1 root bandit5 6118 Jan 11 19:19 spaces file1
-rw-r-----  1 root bandit5 6850 Jan 11 19:19 spaces file2
-rwxr-x---  1 root bandit5 1915 Jan 11 19:19 spaces file3
bandit5@bandit:~/inhere$ file */{.,}* | grep "ASCII text" | grep -v ', with very long lines'
maybehere10/.file2:       ASCII text
maybehere15/.file2:       ASCII text
maybehere01/-file2:       ASCII text
maybehere08/spaces file1: ASCII text
maybehere12/-file2:       ASCII text
maybehere15/spaces file2: ASCII text
maybehere18/-file2:       ASCII text
bandit5@bandit:~/inhere$ find . -type f -size 1033c ! -executable -exec file '{}' \; | grep ASCII
./maybehere07/.file2: ASCII text, with very long lines (1000)
bandit5@bandit:~/inhere$
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

## Notas opcionales.

El comando file */{.,}* devolvería el tipo de archivo de cada archivo en las carpetas en 'inhere'. Usamos */* para imprimir todos los archivos en todos los directorios. Sin embargo, esto no incluye archivos ocultos. Por lo tanto, usamos {.,} para incluir archivos que comienzan con . y , indica archivos que comienzan con cualquier otra cosa 1.

Para hacerlo un poco más visible y concentrarnos solo en los archivos legibles por humanos, podemos usar el comando grep. En este caso, nos gustaría imprimir solo líneas que contengan "ACSII", ya que este es el tipo de archivo legible por humanos que estamos buscando, según el nivel anterior. Para usar este comando, usamos la tubería | para usar grep en la salida del comando de file: file */{.,}* | grepASCII. Ahora, esto sigue siendo una gran cantidad de producción. Concretamente bien texto ASCII, con líneas muy largas y solo texto ASCII.

## Referencias.

https://overthewire.org/wargames/bandit/bandit6.html
https://mayadevbe.me/posts/overthewire/bandit/level6/