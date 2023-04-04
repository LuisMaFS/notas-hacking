# Convertme.py

## Objetivo.

Run the Python script and convert the given number from decimal to binary to get the flag.

## Solución.

**Descargamos el archivo para el reto en la terminal de Kali**

┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/22/convertme.py
.
.
.

**Revisamos el directorio, para ver si se descargó el archivo**

┌──(kali㉿kali)-[~]
└─$ ls
convertme.py  Documents  el       hacking  Pictures  runme.py   Videos
Desktop       Downloads  eltoken  Music    Public    Templates
   

**Ejecutamos la línea puthon3 convertme.py**
┌──(kali㉿kali)-[~]
└─$ python3 convertme.py   
**Nos pide una conraseña para la bandera, ¿Cuál es el número binario equivalente a 99 decimal?**
If 99 is in decimal base, what is it in binary base?
**Con una herramienta de conversión obtenemos el número binario y de paso la bandera**
Answer: 1100011
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_762f748e}

## Notas opcionales.

Python es una herramienta importante en la hacking, con estos retos picoCTF, practicamos su uso.

## Referencias.

https://www.rapidtables.com/convert/number/decimal-to-binary.html