
# fixme1.py

## Objetivo.

Fix the syntax error in this Python script to print the flag.

## Solución.

**Descargamos  el programa python al shell de Kali Linux**

┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/27/fixme1.py  
.
.
.

**Revisamos si se descargo el archivo**
┌──(kali㉿kali)-[~]
└─$ ls
codebook.txt  Desktop    el         hacking   Public     Videos
code.py       Documents  eltoken    Music     runme.py
convertme.py  Downloads  fixme1.py  Pictures  Templates

**Ejecutamos el programa python**
┌──(kali㉿kali)-[~]
└─$ python3 fixme1.py 
  File "/home/kali/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
**Nos dice que hay un error**

**Corregimos el programa**
┌──(kali㉿kali)-[~]
└─$ nano fixme1.py 

**Obtenemos la bandera**
┌──(kali㉿kali)-[~]
└─$ python3 fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}

## Notas opcionales.

Con estos retos podemos seguir practicanado el lenguaje de programación python y sus aplicaciones en la ciberseguridad.

## Referencias.