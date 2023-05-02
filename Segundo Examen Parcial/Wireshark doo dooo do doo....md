# Wireshark doo dooo do doo...

## Objetivo.

Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/0505a462ac9beb7412596855df280f6b/shark1.pcapng).

## Solución.

**Descargar la captura de paquetes y analizarla en wireshark**

**Encontrar el pquete HTTP con la clausula GET**
```
823.7.187055   192.168.38.104   18.222.37.134   HTTP  501GET / HTTP/1.1 

```

**Seguir el stream HTTP**

Encontraremos algo como esto:

```
cvpbPGS{c33xno00_1_f33_h_qrnqorrs}
```

**Desencriptar usando cyberchef ROT13**

```
picoCTF{p33kab00_1_s33_u_deadbeef}
```

## Notas opcionales.

## Referencias.

**Vídeo**

https://www.youtube.com/watch?v=uG42AMp0XHU&ab_channel=MartinCarlisle