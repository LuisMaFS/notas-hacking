# Glory of the garden

## Objetivo.

This [garden](https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg) contains more than it seems.

## Solución.

**Crear y entrar a una carpeta para el reto**
┌──(kali㉿kali)-[~/picoctf/forense]
└─$ mkdir gloryofthegarden
 
┌──(kali㉿kali)-[~/picoctf/forense]
└─$ cd gloryofthegarden 

**Descargar el archivo**
┌──(kali㉿kali)-[~/picoctf/forense/gloryofthegarden]
└─$ wget https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg
--2023-03-26 16:07:16--  https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2295192 (2.2M) [application/octet-stream]
Saving to: ‘garden.jpg’

garden.jpg          100%[================>]   2.19M  2.41MB/s    in 0.9s    

2023-03-26 16:07:18 (2.41 MB/s) - ‘garden.jpg’ saved [2295192/2295192]

**Revisar si el archivo se ha descargado**  
┌──(kali㉿kali)-[~/picoctf/forense/gloryofthegarden]
└─$ ls
garden.jpg

**El reto nos da una pista, esa pista es el uso de un editor hexadecimal**
┌──(kali㉿kali)-[~/picoctf/forense/gloryofthegarden]
└─$ hexeditor garden.jpg 

**Cuando abrimos el editor hexadecimal, nos encontramos con lo siguiente**

**Offset**                               **carácteres hexadecimales**                        **Representación en texto**
00230560   72 65 20 69  73 20 61 20   66 6C 61 67  20 22<font color="red"> 7</font>0 69       e is a flag "pic
00230570   63 6F 43 54  46 7B 6D 6F   72 65 5F 74  68 61 6E 5F       oCTF{more_than_
00230580   6D 33 33 74  73 5F 74 68   65 5F 33 79  33 33 64 64       33ts_the_3y33dd
00230590   32 65 45 46  35 7D 22 0A                                                 2eEF5}".  

**Explicación**
En el editor hexadecimal podemos buscar texto, con la opción de busqueda, se le puede indicar que busque la bandera, sabemos que las banderas comienzan con picoCTF. El número 7 iluminado en rojo, ahi empieza la bandera, esa es la representación hexadecimal de la palabra.

**Bandera**
picoCTF{more_than_m33ts_the_3y33dd2eEF5}

## Notas opcionales.

**Editor Hexadecimal**
Un **editor hexadecimal** (o **editor de archivos binarios**) es un tipo de programa informático "Programa informático") que permite a un usuario modificar archivos binarios. Los editores hexadecimales fueron diseñados para editar sectores de datos de disquetes o discos duros por lo que a veces se llaman "editores de sectores".

## Referencias.

https://es.wikipedia.org/wiki/Editor_hexadecimal
https://www.youtube.com/watch?v=xxhnGxgOtWs&ab_channel=hackadvisermx