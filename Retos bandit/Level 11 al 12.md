# Level 11 al 12

## Objetivo.

La contraseña para el siguiente nivel está almacenada en el archivo **data.txt**, donde todas las letras minúsculas (a-z) y mayúsculas (A-Z) se han girado 13 posiciones.

## Datos de acceso al nivel.

bandit11
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Solución.

bandit11@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 Jan 11 19:18 .
drwxr-xr-x 70 root     root     4096 Jan 11 19:19 ..
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-rw-r-----  1 bandit12 bandit11   49 Jan 11 19:18 data.txt
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr "a-zA-Z" "n-za-mN-ZA-M"
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

bandit11@bandit:~$ python3
Python 3.10.6 (main, Nov 14 2022, 16:10:14) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import codecs
>>> codecs.decode('Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi', 'rot13')
'The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv'

>>> cadena = open('data.txt','r').read()
>>> cadena
'Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi\n'
>>> codecs.decode(cadena, 'rot13')
'The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv\n'

## Notas opcionales.

-tr:  comando para rotar caracteres.

## Referencias.

https://overthewire.org/wargames/bandit/bandit12.html
https://es.wikipedia.org/wiki/ROT13
https://gchq.github.io/CyberChef/
