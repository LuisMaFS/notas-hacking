# The numbers

## Objetivo.

The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?

## Solución.

**Descargar el archivo para el reto**

┌──(kali㉿kali)-[~]

└─$ wget https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png

**Revisar de que tipo de archivo se trata**

┌──(kali㉿kali)-[~]

└─$ file the_numbers.png

the_numbers.png: PNG image data, 774 x 433, 8-bit/color RGB, non-interlaced

*Indica que se trata de una imagen PNG*

**Abrir la imagen**

┌──(kali㉿kali)-[~/picoctf/crypto/thenumbers]

└─$ open the_numbers.png

*La imagen, contiene la bandera pero esta codificada en alfabeto numerico*

Los numeroos son: 16 9 3 15 3 20 6 { 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14 }

Debemos codificarlos par encontrar la bandera

La bandera en su formato quedaría como: picoCTF{thenumbersmason}

## Notas opcionales.

## Referencias.

Vídeo

https://www.youtube.com/watch?v=I95FPcH27j0&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=34&ab_channel=hackadvisermx
