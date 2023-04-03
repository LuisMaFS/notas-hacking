# C0rrupt

## Objetivo.

We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

## Solución.

**Descargar el archivo para el reto**

┌──(kali㉿kali)-[~/picoctf/forense/c0rrupt]

└─$ wget https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery    

**Revisar de que tipo de archivo se trata**

┌──(kali㉿kali)-[~/picoctf/forense/c0rrupt]

└─$ file mystery    

mystery: data

**No dice que tipo de archivo es**

**Ejecutar el comando xxd, para ver los datos hexadecimales de su cabecera**

┌──(kali㉿kali)-[~/picoctf/forense/c0rrupt]

└─$ xxd mystery | head       

00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71 bd2d 8b20 2080 9041 8302 08d0  .d.q.-.  ..A....
00000070: f9ed 40a0 f36e 407b 9023 8f1e d720 8b3e  ..@..n@{.#... .>
00000080: b7c1 0d70 0374 b503 ae41 6bf8 bea8 fbdc  ...p.t...Ak.....
00000090: 3e7d 2a22 336f de5b 55dd 3d3d f920 9188  >}*"3o.[U.==. ..

**El archivo, se trata de un PNG, pero está corrupto hay que repararlo**

**Usamos e editor hexadecimal para cambiar su cabecera**

┌──(kali㉿kali)-[~/picoctf/forense/c0rrupt]

└─$ hexeditor mystery 

00000000  **89 50 4E 47  0D 0A 1A 0A**   00 00 00 0D  43 22 44 52 **PNG**........C"DR

**La cabecera, ha sido cambiada a PNG**

**Revisamos el archivo, con el comando file, pero aún siguen siendo datos**

┌──(kali㉿kali)-[~/picoctf/forense/c0rrupt]

└─$ file mystery 

mystery: data

**Editar el Chunk IHDR en el editor hexadecimal**

┌──(kali㉿kali)-[~/picoctf/forense/C0rrupt]

└─$ hexeditor mystery 

00000000  89 50 4E 47  0D 0A 1A 0A   00 00 00 0D  **49 48 44 52** PNG........**IHDR**

**Checamos el archivo, ya es imagen, pero al abrirla aún sigue corrupta*

┌──(kali㉿kali)-[~/picoctf/forense/C0rrupt]

└─$ file mystery      

mystery: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced

**Instalar herramienta que nos ayude a verificar que hay de malo en una imagen png**

┌──(kali㉿kali)-[~/picoctf/forense/C0rrupt]

└─$ sudo apt install pngcheck   

**Revisar el daño**

┌──(kali㉿kali)-[~/picoctf/forense/C0rrupt]

└─$ pngcheck -v mystery

	File: mystery (202940 bytes)
	  chunk IHDR at offset 0x0000c, length 13
	1642 x 1095 image, 24-bit RGB, non-interlaced
	  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
	  chunk gAMA at offset 0x00032, length 4: 0.45455
	  chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
	  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
	ERRORS DETECTED in mystery

**Dice que el error está en el chunk pHYs**

**Reparamos el error**

00000040  00 09 70 48  59 73 **00** 00   16 25 00 00  16 25 01 49          ..pHYs...%...%.I

**Volvemos a revisar**

┌──(kali㉿kali)-[~/picoctf/forense/C0rrupt]

└─$ pngcheck -v mystery

	File: mystery (202940 bytes)
	  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
	  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
	chunk gAMA at offset 0x00032, length 4: 0.45455
	chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
	:  invalid chunk length (too large)
	ERRORS DETECTED in mystery

**Volvemos a reparar**

00000050  52 24 F0 AA  AA FF A5 **49   44 41** 54 78  5E EC BD 3F          R$.....**IDAT**x^..?

**Reparamos la dimensión del chunk**

00000050  52 24 F0 **00  00** FF A5 49   44 41 54 78  5E EC BD 3F          R$.....IDATx^..?

**Checar si no hay errores**

┌──(kali㉿kali)-[~/picoctf/forense/C0rrupt]

└─$ pngcheck -v mystery

	File: mystery (202940 bytes)
	  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
	  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
	  chunk gAMA at offset 0x00032, length 4: 0.45455
	  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
	  chunk IDAT at offset 0x00057, length 65445
    zlib: deflated, 32K window, fast compression
	  chunk IDAT at offset 0x10008, length 65524
	  chunk IDAT at offset 0x20008, length 65524
	  chunk IDAT at offset 0x30008, length 6304
	  chunk IEND at offset 0x318b4, length 0
	No errors detected in mystery (9 chunks, 96.3% compression).

**Abrimos la imagen para ver la bandera**

┌──(kali㉿kali)-[~/picoctf/forense/C0rrupt]

└─$ open mystery

**Bandera**

picoCTF{c0rrupt10n_1847995}


## Notas opcionales.

## Referencias.

https://www.youtube.com/watch?v=7zY4VkiWbBI&t=63s&ab_channel=hackadvisermx
https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbHI3T0lrdy1DT2hQM24tanl4X1hjYTVLc3FHd3xBQ3Jtc0ttVnBRNmp0RHlMSEw3VnRhbngtUEZKVWVCaXBxUmswWkl0WURLdDNJYmRnbmJMOTdpVkpXYUVCdjlsYWt3OS0yaVpELWRuZmZfMXhUNXZIOHBwbHdXRzh2YlFLVndBUmRNa3ZYa3FDdVNkRlJZTndYMA&q=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FList_of_file_signatures&v=7zY4VkiWbBI
