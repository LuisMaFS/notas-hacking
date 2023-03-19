# What's a net cat?

## Objetivo.

Using netcat (nc) is going to be pretty important. Can you connect to `jupiter.challenges.picoctf.org` at port `41120` to get the flag?

## Solución.

Usando la ventana de comandos de kali linux, usando netcat conectandose a jupiter.challenges.picoctf.org en el puerto 41120 obtenemos la bandera

┌──(kali㉿kali)-[~]
└─$ netcat jupiter.challenges.picoctf.org 41120   
You're on your way to becoming the net cat master
picoCTF{nEtCat_Mast3ry_3214be47}

## Notas opcionales.

Netcat es una herramienta de la línea de comandos que se utiliza para restablecer conexiones de tipo TCP y UDP. Además, permite hacer escaneo de puertos, direcciones IP y ver qué servicios se encuentran activos

## Referencias.

https://keepcoding.io/blog/que-es-netcat/#:~:text=Netcat%20es%20una%20herramienta%20de,qu%C3%A9%20servicios%20se%20encuentran%20activos.