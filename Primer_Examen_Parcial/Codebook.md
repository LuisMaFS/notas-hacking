# Codebook

## Objetivo.

Run the Python script `code.py` in the same directory as `codebook.txt`.

## Solución.

**Descargamos el archivo python  en la terminal de Kali**
┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/3/code.py      
.
.
.

**Ejecutamos el programa python**
┌──(kali㉿kali)-[~]
└─$ python3 code.py     
Couldn't find codebook.txt. Did you download that file into the same directory as this script?
**Dice que no funciona, falta el archivo codebook.txt**

**Descargamos el archivo de texto codebook.txt**
┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/3/codebook.txt
.
.
.

**Revisamos si todos los archivos se han descargado en el directorio**
┌──(kali㉿kali)-[~]
└─$ ls
codebook.txt  Desktop    el       Music     runme.py
code.py       Documents  eltoken  Pictures  Templates
convertme.py  Downloads  hacking  Public    Videos

**Ejecutamos el programa python  y esto nos lleva a la bandera**
┌──(kali㉿kali)-[~]
└─$ python3 code.py                                    
picoCTF{c0d3b00k_455157_197a982c}

## Notas opcionales.

Python es un lenguaje de programación, podemos hacer programas que utilizen archivos para su funcionamiento, como el caso en este reto. Es bueno recordar el uso de las herramientas que se disponen para el hacking.

## Referencias.