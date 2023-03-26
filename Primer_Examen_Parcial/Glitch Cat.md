# Glitch Cat

## Objetivo.

Our flag printing service has started glitching!`$ nc saturn.picoctf.net 53638`

## Solución.

**Conección al servidor usando netcat**

┌──(kali㉿kali)-[~]
└─$ nc saturn.picoctf.net 53638
'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'
**Obtenemos la bandera, pero está incompleta hay que completarla**

**Python nos ayuda a formar la cadena y así obtener la bandera**
┌──(kali㉿kali)-[~]
└─$ python           
Python 3.11.2 (main, Feb 12 2023, 00:48:52) [GCC 12.2.0] on linux

**>>>** x = 'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'
**>>>** x
'picoCTF{gl17ch_m3_n07_bda68f75}'

## Notas opcionales.

## Referencias.


