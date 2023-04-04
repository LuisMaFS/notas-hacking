# Matryoshka doll

## Objetivo.

Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/205adad23bf9d8303081a0e71c9beab8/dolls.jpg)

## Solución.

**Parece que hay archivos, dentro de la imagen, usemos binwalk, para ver que hay dentro**

┌──(kali㉿kali)-[~/picoctf/forensic/matryoshkadoll]

└─$ binwalk dolls.jpg 


DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------

0                                 0x0                                         PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced

3226                           0xC9A                                    TIFF image data, big-endian, offset of first image directory: 8

272492                      0x4286C                                  Zip archive data, at least v2.0 to extract, compressed size: 378952, uncompressed size: 383937, name: base_images/2_c.jpg

651610                      0x9F15A                                  End of Zip archive, footer length: 22

**Descomprimir la imagen**

┌──(kali㉿kali)-[~/picoctf/forensic/matryoshkadoll]

└─$ binwalk -e  dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------

0                                 0x0                                         PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced

3226                           0xC9A                                    TIFF image data, big-endian, offset of first image directory: 8

272492                      0x4286C                                  Zip archive data, at least v2.0 to extract, compressed size: 378952, uncompressed size: 383937, name: base_images/2_c.jpg

651610                      0x9F15A                                  End of Zip archive, footer length: 22


┌──(kali㉿kali)-[~/picoctf/forensic/matryoshkadoll]

└─$ ls

dolls.jpg  _dolls.jpg.extracted

**Entrar a la subcarpeta generada**

┌──(kali㉿kali)-[~/picoctf/forensic/matryoshkadoll]

└─$ cd _dolls.jpg.extracted 

┌──(kali㉿kali)-[~/picoctf/forensic/matryoshkadoll/_dolls.jpg.extracted]

└─$ ls

4286C.zip  base_images

**Entrar a la subcarpeta base_images**

┌──(kali㉿kali)-[~/picoctf/forensic/matryoshkadoll/_dolls.jpg.extracted]

└─$ cd base_images         


┌──(kali㉿kali)-[~/…/forensic/matryoshkadoll/_dolls.jpg.extracted/base_images]                                                                            

└─$ ls

2_c.jpg

**Abrir la imagen**

┌──(kali㉿kali)-[~/…/forensic/matryoshkadoll/_dolls.jpg.extracted/base_images]                                                                            

└─$ open 2_c.jpg 

**Repetir el proceso**

┌──(kali㉿kali)-[~/…/forensic/matryoshkadoll/_dolls.jpg.extracted/base_images]                                                                            

└─$ binwalk 2_c.jpg      

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------

0                                  0x0                                        PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced

3226                            0xC9A                                    TIFF image data, big-endian, offset of first image directory: 8

187707                        0x2DD3B                               Zip archive data, at least v2.0 to extract, compressed size: 196042, uncompressed size: 201444, name: base_images/3_c.jpg

383804                        0x5DB3C                               End of Zip archive, footer length: 22

383915                       0x5DBAB                                End of Zip archive, footer length: 22



┌──(kali㉿kali)-[~/…/forensic/matryoshkadoll/_dolls.jpg.extracted/base_images]                                                                            

└─$ binwalk -e  2_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------

0                                  0x0                                        PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced

3226                            0xC9A                                    TIFF image data, big-endian, offset of first image directory: 8

187707                        0x2DD3B                               Zip archive data, at least v2.0 to extract, compressed size: 196042, uncompressed size: 201444, name: base_images/3_c.jpg

383804                        0x5DB3C                               End of Zip archive, footer length: 22

383915                       0x5DBAB                                End of Zip archive, footer length: 22

┌──(kali㉿kali)-[~/…/forensic/matryoshkadoll/_dolls.jpg.extracted/base_images]                                                                            

└─$ ls

2_c.jpg  _2_c.jpg.extracted


┌──(kali㉿kali)-[~/…/forensic/matryoshkadoll/_dolls.jpg.extracted/base_images]                                                                            

└─$ cd _2_c.jpg.extracted/base_images 
 

┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]

└─$ ls
3_c.jpg
 

┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]

└─$ open 3_c.jpg 

**Repetir el proceso una vez más**
**Esto se repitió unas 4 veces más**

┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]

└─$ binwalk -e  4_c.jpg

┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]

└─$ ls

4_c.jpg  _4_c.jpg.extracted

┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]

└─$ _4_c.jpg.extracted 

┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]

└─$ ls

136DA.zip  flag.txt

**Abrimos el archivo flag.txt**

┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]

└─$ cat flag.txt 

picoCTF{96fac089316e094d41ea046900197662} 


## Notas opcionales.

## Referencias.

**Vídeo**

https://www.youtube.com/watch?v=NkbtA7x5aVI&ab_channel=hackadvisermx