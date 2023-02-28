# Level 18 al 19

## Objetivo.

La contraseña para el siguiente nivel se almacena en un archivo ReadMe en el Homedirectory. Desafortunadamente, alguien ha modificado .BASHRC para iniciar sesión cuando inicia sesión con SSH.

## Datos de acceso al nivel.

bandit18
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

## Solución.

C:\Users\Acer>ssh bandit18@bandit.labs.overthewire.org -p 2220 ls



                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password:
readme

C:\Users\Acer>$ ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
"$" no se reconoce como un comando interno o externo,
programa o archivo por lotes ejecutable.

C:\Users\Acer>ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password:
awhqfNnAbc1naukrpqDYcF95h7HoMTrC

## Notas opcionales.

En lugar de iniciar sesión en la máquina con SSH, ejecutamos un comando a través de SSH. Primero, usamos LS para asegurarnos de que el archivo ReadMe esté en la carpeta de lo que podemos usar CAT para leerlo.

## Referencias.

https://overthewire.org/wargames/bandit/bandit19.html
https://mayadevbe.me/posts/overthewire/bandit/level19/