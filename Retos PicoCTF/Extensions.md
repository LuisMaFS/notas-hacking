# Extensions

## Objetivo.

This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

## Solución.

**Crear y entrar a una subcarpeta para realizar el reto**
┌──(kali㉿kali)-[~/picoctf/forense]
└─$ mkdir extensions  

┌──(kali㉿kali)-[~/picoctf/forense]
└─$ cd extensions 

**Descargar el archivo para el reto**
┌──(kali㉿kali)-[~/picoctf/forense/extensions]
└─$ wget https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt
--2023-03-27 00:26:31--  https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 9984 (9.8K) [application/octet-stream]
Saving to: ‘flag.txt’

flag.txt            100%[================>]   9.75K  --.-KB/s    in 0s      

2023-03-27 00:26:36 (153 MB/s) - ‘flag.txt’ saved [9984/9984]

**Revisar de que archivo se trata, a pesar de tener extensión txt, en realidad se trata de una imagen png**
┌──(kali㉿kali)-[~/picoctf/forense/extensions]
└─$ file flag.txt 
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced

**Revisamos la firma (magic byte) del archivo y efectivamente el archivo, es una imagen png**
**<font color="red"> 89 50 4E </font>**
┌──(kali㉿kali)-[~/picoctf/forense/extensions]
└─$ xxd flag.txt | head
00000000: <font color="red">8950 4e</font>47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR
00000010: 0000 06a1 0000 0260 0802 0000 0085 ad5e  .......`.......^
00000020: 9a00 0000 0173 5247 4200 aece 1ce9 0000  .....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 0000 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f000 0026 9549 4441 5478 5eed dd6b  R$...&.IDATx^..k
00000060: 421b 39b7 05d0 3b2e 0694 f130 9a4c 2683  B.9...;....0.L&.
00000070: f9ae 5f80 4e3d 25bb 4cb3 f15a bfba a14a  .._.N=%.L..Z...J
00000080: 7574 2413 7927 c0ff fd0f 0000 0000 4826  ut$.y'........H&
00000090: e303 0000 0080 6c32 3e00 0000 00c8 26e3  ......l2>.....&.

**Le cambiamos la extensión al archivo**
┌──(kali㉿kali)-[~/picoctf/forense/extensions]
└─$ mv flag.txt flag.png

**Abrimos la imagen**
┌──(kali㉿kali)-[~/picoctf/forense/extensions]
└─$ open flag.png 

**Obtenemos la bandera**
picoCTF{now_you_know_about_extensions}

## Notas opcionales.

**Formato de archivo**
Un **formato de archivo** es una especificación que define la forma en que la información se organiza y se codifica en un archivo informático. Dado que una unidad de disco o de cualquier memoria solo puede almacenar bits, el ordenador o computadora debe tener algún método para convertir la información (ceros y unos). Existen diversos tipos de formatos para diferentes tipos de archivos que puedan ser usados. No obstante, cada tipo de archivo puede almacenarse en una variedad de formatos adicionales añadiendo información y haciendo que la forma de trabajarlos sea más compleja ya que se almacenan en diferentes formatos.

## Referencias.

https://es.wikipedia.org/wiki/Pcap_(interfaz)#:~:text=El%20pcap%20es%20una%20interfaz,recibe%20el%20nombre%20de%20WinPcap.
https://www.youtube.com/watch?v=q8cM4sY0izw&ab_channel=hackadvisermx