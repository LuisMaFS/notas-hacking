# Packets Primer

## Objetivo.

Download the packet capture file and use packet analysis software to find the flag.

-   [Download packet capture](https://artifacts.picoctf.net/c/195/network-dump.flag.pcap)

## Solución.

**Descargar la captura de paquetes y analizarla en wireshark**

**Seguir el stream del primer paquete TCP**

Ahí encontramos la bandera
```
p i c o C T F { p 4 c k 3 7 _ 5 h 4 r k _ b 9 d 5 3 7 6 5 }

```

**Con python eliminamos los espacios**

```
picoCTF{p4ck37_5h4rk_b9d53765}
```

## Notas opcionales.

## Referencias.

**Vídeo**

https://www.youtube.com/watch?v=QL5AeBprNMs&ab_channel=AlmondForce