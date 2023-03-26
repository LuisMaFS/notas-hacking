# First Grep

## Objetivo.

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file)? This would be really tedious to look through manually, something tells me there is a better way.

## Solución.

frausto_san-picoctf@webshell:~$ cd fg
frausto_san-picoctf@webshell:~/fg$ cat file
...
picoCTF{grep_is_good_to_find_things_5af9d829}


Copiamos el enlace que proporciona la página. abrimos el webshell de picoCTF. 
Creamos una carpeta llamda fg con el comando mkdir, luego ingresamos a ella con cd, y con el comando wget pegando el url del archivo copiado. Se descarga el archivo en la carpeta.

hacemos cat y arroja muchas opciones, entonces con el comando grep y pico obtenemos la bandera

## Notas opcionales.

recordemos que grep se utiliza muy a menudo como "filtro" con otros comando. Esto le permite filtrar y eliminar la información inútil que se produce tras ejecutar un comando. Para usar grep como filtro, debe enviar el resultado del comando mediante grep por el canal de comunicación. El símbolo para el canal de comunicación es " | ".

## Referencias.

https://www.youtube.com/watch?v=ajY1Cqag8EQ&ab_channel=SanjinDedic
https://docs.oracle.com/cd/E19620-01/805-7644/6j76klop3/index.html#:~:text=grep%20se%20utiliza%20muy%20a,de%20comunicaci%C3%B3n%20es%20%22%20%7C%20%22.