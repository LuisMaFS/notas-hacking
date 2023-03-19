# Obedient Cat

## Objetivo.

This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/2d24d50b4ebed90c704575627f1f57b2/flag).

## Solución.

Abrir el webshell de picoCTF.
Y descargamos el archivo llamado **flag** en el shell usando wget.
Y para ver el contenido del archivo **flag** se escribe el comando cat seguido deñ archivo.
Observamos que nos regresa la bandera.

frausto_san-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/2d24d50b4ebed90c704575627f1f57b2/flag
--2023-03-15 00:04:16--  https://mercury.picoctf.net/static/2d24d50b4ebed90c704575627f1f57b2/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag'

flag                    100%[============================>]      34  --.-KB/s    in 0s      

2023-03-15 00:04:16 (15.5 MB/s) - 'flag' saved [34/34]

frausto_san-picoctf@webshell:~$ ls
README.txt  fg  flag  strings  strings.1
frausto_san-picoctf@webshell:~$ cat flag

## Notas opcionales.

Cat es la abreviatura de **concatenar**. Esto se refiere al hecho de que cat puede ser utilizado para combinar múltiples archivos en un archivo, también se puede utilizar para crear nuevos archivos y para mostrar el contenido de los archivos existentes.

## Referencias.

https://play.picoctf.org/practice
https://www.dongee.com/tutoriales/comando-cat-linux/