# So Meta

## Objetivo.

Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png).

## Solución.

**Creamos una subcarpeta para el reto**
┌──(kali㉿kali)-[~/picoctf/forense]
└─$ cd someta 

**Descargamos la imagen a la carpeta**
┌──(kali㉿kali)-[~/picoctf/forense/someta]
└─$ wget https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png
--2023-03-26 20:12:19--  https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108795 (106K) [application/octet-stream]
Saving to: ‘pico_img.png’

pico_img.png          100%[=========================>] 106.25K  --.-KB/s    in 0.1s    

2023-03-26 20:12:25 (856 KB/s) - ‘pico_img.png’ saved [108795/108795]

**Revisamos si se descargó la imagen**
┌──(kali㉿kali)-[~/picoctf/forense/someta]
└─$ ls
pico_img.png

**Con exiftool podemos ver los metadatos**
┌──(kali㉿kali)-[~/picoctf/forense/someta]
└─$ exiftool pico_img.png 
ExifTool Version Number         : 12.57
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2020:10:26 14:38:23-04:00
File Access Date/Time           : 2023:03:26 20:12:25-04:00
File Inode Change Date/Time     : 2023:03:26 20:12:25-04:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Warning                         : [minor] Text/EXIF chunk(s) found after PNG IDAT (may be ignored by some readers)
Artist                          : <font color="red"> picoCTF{s0_m3ta_d8944929}</font>
Image Size                      : 600x600
Megapixels                      : 0.360


**El metadato artista, nos da la bandera**

## Notas opcionales.

Los metadatos, literalmente «sobre datos», son datos que describen otros datos. En general, un grupo de metadatos se refiere a un grupo de datos que describen el contenido informativo de un objeto al que se denomina recurso.

## Referencias.

https://es.wikipedia.org/wiki/Metadatos
https://www.youtube.com/watch?v=Govu_p-wf4I&ab_channel=hackadvisermx
