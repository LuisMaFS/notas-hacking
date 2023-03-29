## Descripción
Every file gets a flag. The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/489/flag.png).

## Hints



## Solución
``` bash
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $ls
encrypted.txt  readmycert.csr  Rotation.md
flag.png       ReadMyCert.md   Untitled.md
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $file flag.png 
flag.png: PNG image data, 512 x 504, 8-bit/color RGBA, non-interlaced
┌┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $exiftool flag.png 
ExifTool Version Number         : 12.16
File Name                       : flag.png
Directory                       : .
File Size                       : 42 KiB
File Modification Date/Time     : 2023:03:14 14:34:03-06:00
File Access Date/Time           : 2023:03:14 14:34:03-06:00
File Inode Change Date/Time     : 2023:03:14 14:34:06-06:00
File Permissions                : rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 512
Image Height                    : 504
Bit Depth                       : 8
Color Type                      : RGB with Alpha
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Warning                         : [minor] Trailer data after PNG IEND chunk
Image Size                      : 512x504
Megapixels                      : 0.258
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $binwalk flag.png 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2832, uncompressed size: 2984, name: secret/flag.png
42871         0xA777          End of Zip archive, footer length: 22

┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $binwalk -e flag.png 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2832, uncompressed size: 2984, name: secret/flag.png
42871         0xA777          End of Zip archive, footer length: 22

┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $ls 
encrypted.txt  _flag.png.extracted  ReadMyCert.md  Untitled.md
flag.png       readmycert.csr       Rotation.md
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $cd _flag.png.extracted/
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/_flag.png.extracted]
└──╼ $ls -la 
total 48
drwxr-xr-x 1 ramdark ramdark    46 mar 14 14:36 .
drwxr-xr-x 1 ramdark ramdark   178 mar 14 14:36 ..
-rw-r--r-- 1 ramdark ramdark     0 mar 14 14:36 29
-rw-r--r-- 1 ramdark ramdark 42852 mar 14 14:36 29.zlib
-rw-r--r-- 1 ramdark ramdark  3154 mar 14 14:36 9B3B.zip
drwxr-xr-x 1 ramdark ramdark    16 mar 11 20:24 secret
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/_flag.png.extracted]
└──╼ $cd secret
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/_flag.png.extracted/secret]
└──╼ $ls -la
total 4
drwxr-xr-x 1 ramdark ramdark   16 mar 11 20:24 .
drwxr-xr-x 1 ramdark ramdark   46 mar 14 14:36 ..
-rw-r--r-- 1 ramdark ramdark 2984 mar 11 20:24 flag.png
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/_flag.png.extracted/secret]
└──╼ $


```


## Flag

``` picoCTF{Hiddinng_An_imag3_within_@n_ima9e_c31884c7} ```


## Notas adicionales

Al utilizar el comando binwalk nos damos cuenta de que tiene información que puede extraerse, se extrae el archvio dando un directorio. al entrar al directorio nos topamos con una imagen en formato png que esta, trae la bandera. 


|Comando | Descripcion |
|------------ | ------------|
| exiftool | permite leer y escribir meta informacion en archivos |
|binwalk |permite buscar imagenes binarias de archivos embebidos y codigo ejecutable|
|-e |extrae archivos ocultos|





## Referencias
+ [Binwalk](https://www.kali.org/tools/binwalk/)
