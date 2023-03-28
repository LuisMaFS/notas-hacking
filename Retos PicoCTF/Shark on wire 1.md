# Shark on wire 1

## Objetivo.

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

## Solución.

**Para este reto usaremos un sniffer de red, este programa que rastrea paquetes de la red se llama wireshark**
**Descargamos la captura de paquetes que nos da el reto**

**Dentro de la captura de paquetes, seguimos el stream de paquetes UDP**

**El stream 6 nos da la bandera para el reto**
picoCTF{StaT31355_636f6e6e}

## Notas opcionales.

**PCAP**
El pcap es una **interfaz de una aplicación de programación para captura de paquetes**. La implementación del pcap para sistemas basados en Unix se conoce como libpcap; el port para Windows del libpcap recibe el nombre de WinPcap.

## Referencias.

https://es.wikipedia.org/wiki/Pcap_(interfaz)#:~:text=El%20pcap%20es%20una%20interfaz,recibe%20el%20nombre%20de%20WinPcap.
https://www.youtube.com/watch?v=q8cM4sY0izw&ab_channel=hackadvisermx
