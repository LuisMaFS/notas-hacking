# Level 17 al 18

## Objetivo.

Hay 2 archivos en el Home directory: passwords.old y passwords.new. La contraseña para el siguiente nivel está en passwords.new.  y es la única línea que se ha cambiado entre passwords.old and passwords.new.

Nota: Si ha resuelto este nivel y vea "¡Byebye!" when trying to log into bandit18, this is related to the next level, bandit19

## Datos de acceso al nivel.

bandit17
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e

## Solución.

bandit17@bandit:~$ ls
passwords.new  passwords.old
bandit17@bandit:~$ diff passwords.old passwords.new
42c42
###### f9wS9ZUDvZoo3PooHgYuuWdawDFvGld2
---
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

## Notas opcionales.

El comando diff imprime la diferencia entre dos archivos

## Referencias.

https://overthewire.org/wargames/bandit/bandit18.html
https://mayadevbe.me/posts/overthewire/bandit/level18/