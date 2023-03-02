# Level 26 al 27

## Objetivo.

¡Buen trabajo consiguiendo el shell! ¡Ahora date prisa y obtén la contraseña para bandit27!

## Datos de acceso al nivel.

bandit26
p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

## Solución.

:shell
bandit26@bandit:~$ ls
bandit27-do  text.txt
bandit26@bandit:~$ ./bandit27-do id
uid=11026(bandit26) gid=11026(bandit26) euid=11027(bandit27) groups=11026(bandit26)
bandit26@bandit:~$  ./bandit27-do cat /etc/bandit_pass/bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

## Notas opcionales.

Se necesita la solución del nivel 26 para obtener el shell para bandit26.

Una vez que tenemos el shell, podemos encontrar un archivo llamado bandit27-do en el directorio de inicio de bandit26. El nombre sugiere que eso es lo que necesitamos revisar.

Ejecutamos el mismo comando que en el nivel 20 y obtenemos el password.

## Referencias.

https://overthewire.org/wargames/bandit/bandit27.html
https://ingsoftware.reduaz.mx/moodle/mod/resource/view.php?id=36056