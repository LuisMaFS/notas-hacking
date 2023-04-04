# Tunn3l v1s10n

## Objetivo.

We found this [file](https://mercury.picoctf.net/static/09a86202e72dbdb5bf4d1b5d2c6a5b86/tunn3l_v1s10n). Recover the flag.

## Solución.

**Descargar el archivo para el reto** 

**Revisar su tipo**

┌──(kali㉿kali)-[~/picoctf/forensic/tunnelvision]

└─$ file tunn3l_v1s10n 

tunn3l_v1s10n: data

**Son datos**

**Hay que checar su encabezado**

┌──(kali㉿kali)-[~/picoctf/forensic/tunnelvision]

└─$ xxd tunn3l_v1s10n | head

00000000:  424d 8e26 2c00 0000 0000 bad0 0000 bad0  BM.&,...........

00000010:  0000 6e04 0000 3201 0000 0100 1800 0000  ..n...2.........

00000020:  0000 5826 2c00 2516 0000 2516 0000 0000  ..X&,.%...%.....

00000030:  0000 0000 0000 231a 1727 1e1b 2920 1d2a  ......#..'..) .*

00000040:  211e 261d 1a31 2825 352c 2933 2a27 382f  !.&..1(%5,)3*'8/

00000050:  2c2f 2623 332a 262d 2420 3b32 2e32 2925  ,/&#3*&-$ ;2.2)%

00000060:  3027 2333 2a26 382c 2836 2b27 392d 2b2f  0'#3*&8,(6+'9-+/

00000070:  2623 1d12 0e23 1711 2916 0e55 3d31 9776  &#...#..)..U=1.v

00000080:  668b 6652 996d 569e 7058 9e6f 549c 6f54  f.fR.mV.pX.oT.oT

00000090:  ab7e 63ba 8c6d bd8a 69c8 9771 c193 71c1  .~c..m..i..q..q.

**En efecto los datos están ofuscados**

**Con el editor hexadecimal, moficar el oofset 0E y 0A**

┌──(kali㉿kali)-[~/picoctf/forensic/tunnelvision]

└─$ hexeditor tunn3l_v1s10n 

00000000  42 4D 8E 26  2C 00 00 00   00 00 **28 00**  00 00 **28 00**                       BM.&,.....(...(.

**Abrimos la imagen**

┌──(kali㉿kali)-[~/picoctf/forensic/tunnelvision]

└─$ open tunn3l_v1s10n 

**Ya abre. pero no hay bandera**

┌──(kali㉿kali)-[~/picoctf/forensic/tunnelvision]

└─$ hexeditor tunn3l_v1s10n 

**Hay que modificar el tamño de la imagen, para poder ver la bandera, en el offset 12**

00000010:  0000 6e04 0000 **4004** 0000 0100 1800 0000  ..n...2.........

**Volvemos abrir la imagen y obtenemos la bandera**

┌──(kali㉿kali)-[~/picoctf/forensic/tunnelvision]

└─$ open tunn3l_v1s10n 

**Bandera**

picoCTF{qu1t3_a_v13w_2020}

## Notas opcionales.


## Referencias.

**Video**

https://www.youtube.com/watch?v=1ucy2G1PIh4&ab_channel=hackadvisermx