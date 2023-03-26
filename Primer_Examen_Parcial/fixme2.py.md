
# fixme2.py

## Objetivo.

Fix the syntax error in the Python script to print the flag.

## Solución.

**Descargamos  el programa python al shell de Kali Linux**

┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/27/fixme2.py  
.
.
.

**Revisamos si se descargo el archivo**
┌──(kali㉿kali)-[~]
└─$ ls
codebook.txt  Desktop    el         fixme2.py  Pictures  Templates
code.py       Documents  eltoken    hacking    Public    Videos
convertme.py  Downloads  fixme1.py  Music      runme.py

**Ejecutamos el programa python**
┌──(kali㉿kali)-[~]
└─$ python3 fixme2.pys
python3: can't open file '/home/kali/fixme2.pys': [Errno 2] No such file or directory

**Nos dice que no puede abrir el programa python**

**Corregimos el programa**
┌──(kali㉿kali)-[~]
└─$ mousepad fixme2.py 

**La corrección se hace en esta seccion del código**

if flag ="":
  print('String XOR encountered a problem, quitting.')
else:
  print('That is correct! Here\'s your flag: ' + flag)

**Cambiamos el único signo igual, por dos signos iguales**

**Obtenemos la bandera**
┌──(kali㉿kali)-[~]
└─$ python3 fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}

## Notas opcionales.

Con estos retos podemos seguir practicanado el lenguaje de programación python y sus aplicaciones en la ciberseguridad.

## Referencias.