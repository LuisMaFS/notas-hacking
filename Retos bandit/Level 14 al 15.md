# Level 14 al 15

## Objetivo.

La contraseña para el siguiente nivel se puede recuperar enviando la contraseña del nivel actual al puerto 30000 en localhost.

## Datos de acceso al nivel.

bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

## Solución.

bandit14@bandit:~$ nc -v localhost 30000
Connection to localhost (127.0.0.1) 30000 port [tcp/*] succeeded!
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Notas opcionales.

Usamos netcat para conectarnos al localhost 30000. Ingresamos la contraseña del reto anterior
Y nos regresa la contraseña.

## Referencias.

https://overthewire.org/wargames/bandit/bandit15.html
