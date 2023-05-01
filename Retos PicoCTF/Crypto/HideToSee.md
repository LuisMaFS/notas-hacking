# HideToSee

## Objetivo.

How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/238/atbash.jpg).

## Solución.

**Descargar el archivo de texto para el reto**

┌──(kali㉿kali)-[~/picoctf/crypto/hidetosee]

└─$ wget https://artifacts.picoctf.net/c/238/atbash.jpg 

**Usamos el comando steghide y nos generará un archivo llamado encrypted.txt**

┌──(kali㉿kali)-[~/picoctf/crypto/hidetosee]

└─$ steghide extract -sf atbash.jpg 

Enter passphrase: 

wrote extracted data to "encrypted.txt".

**Hacemos un cat a encrypted.txt**

┌──(kali㉿kali)-[~/picoctf/crypto/hidetosee]

└─$ cat encrypted.txt 

krxlXGU{zgyzhs_xizxp_8z0uvwwx}

**Usando cyberchef podemos obtener la bandera**

**Bandera** picoCTF{atbash_crack_8a0feddc}
## Notas opcionales.

## Referencias.

**Vídeo**

https://www.youtube.com/watch?v=iNcta36CavA&ab_channel=AlmondForce