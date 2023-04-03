# Shark on wire 2

## Objetivo.

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

## Solución.

**Para este reto usaremos wireshark**
**Descargamos la captura de paquetes que nos da el reto**

**Dentro de la captura de paquetes, seguimos el stream de paquetes UDP**

**El stream 32 es el inicio de la "bandera" y el stream 60 el final**

**El puerto origen es el 5000 y el puerto destino el 22**

**Podemos filtrar los paquetes UDP, dirigidos al puerto 22 con:**

udp.dstport == 22 

Se puede notar que el stream de paquetes empieza en el 5000 y termina en el 5000

Hay que descifrar la bandera de acuerdo a los números que siguen después del primer 5000, en este caso es 5112, tomamos el 112 y lo convertimos de hexadecimal a ASCII para saber que carácter es. Aquí podemos apoyarnos de un decodificador o de python

**Python**

frausto_san-picoctf@webshell:~/picoctf/forensics$ python3

Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux

Type "help", "copyright", "credits" or "license" for more information.

**>>>** chr(112)
'p'

**>>>** chr(105)
'i'

**>>>** chr(99))
'c'

**>>>** chr(111)
'o'

**>>>** chr(67)
'C'

**>>>** chr(84)
'T'

**>>>** chr(70)
'F'

**>>>** chr(123)
'{'

**>>>** chr(112)
'p'

**>>>** chr(49)
'1'

**>>>** chr(76)
'L'

**>>>** chr(76)
'L'

**>>>** chr(102)
'f'

**>>>** chr(51)
'3'

**>>>** chr(114)
'r'

**>>>** chr(51)
'3'

**>>>** chr(100)
'd'

**>>>** chr(95)
'_'

**>>>** chr(100)
'd'

**>>>** chr(97)
'a'

**>>>** chr(116)
't'

**>>>** chr(97)
'a'

**>>>** chr(95)
'_'

**>>>** chr(118)
'v'

**>>>** chr(49)
'1'

**>>>** chr(97)
'a'

**>>>** chr(95)
'_'

**>>>** chr(115)
's'

**>>>** chr(116)
't'


**>>>** chr(51)
'3'

**>>>** chr(103)
'g'

**>>>** chr(48)
'0'

**>>>** chr(125)
'}'

**Organizar la bandera**

picoCTF{p1LLf3red_data_v1a_st3g0}

## Notas opcionales.


## Referencias.

https://www.youtube.com/watch?v=WcMl1SvQ6hI&ab_channel=hackadvisermx