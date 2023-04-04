# WebNet1

## Objetivo.

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

## Solución.

**Similar al reto anterior**
**Descargar la captura de paquetes y la llave que proporciona el reto**

**Los streams TLS, están encriptados, usando la llave podemos acceder a su contenido**

**En wireshark debemos editar las preferencias y escojer como protocolo TLS, después incluir la llave**
**Los paquetes se han desencriptado, se observa que se ha descargado una imagen en el PCAP, podemos exportar dicho objeto**

**Cuando este guardada la imagen, hay que abrirla y examinar que contiene**

┌──(kali㉿kali)-[~/picoctf/forensic/webnet1]

└─$ open vulture.jpg 

**Con strings podemos ver sus cadenas y ahí contiene la bandera**

┌──(kali㉿kali)-[~/picoctf/forensic/webnet1]

└─$ strings vulture.jpg 

JFIF

Exif

picoCTF{honey.roasted.peanuts}

## Notas opcionales.

## Referencias.

**Vídeo**

https://www.youtube.com/watch?v=Ym3i79nEHjw&ab_channel=hackadvisermx

