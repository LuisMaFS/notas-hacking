# Level 25 al 26

## Objetivo.

Iniciar sesión en bandit26 desde bandit25 debería ser bastante fácil... El shell para el usuario bandit26 no es /bin/bash, sino otra cosa. Descubra qué es, cómo funciona y cómo salir de él.

## Datos de acceso al nivel.

bandit25
p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

## Solución.

bandit25@bandit:~$ ls
bandit26.sshkey
bandit25@bandit:~$  ssh -i bandit26.sshkey bandit26@localhost -p 2220
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
.
.
.
Could not create directory '/home/bandit25/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit25/.ssh/known_hosts).
Connection to localhost closed.
bandit25@bandit:~$  cat /etc/passwd | grep bandit26
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
bandit25@bandit:~$ cat /usr/bin/showtext
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0
bandit25@bandit:~$  ssh -i bandit26.sshkey bandit26@localhost -p 2220
  _                     _ _ _   ___   __
 | |                   | (_) | |__ \ / /
 | |__   __ _ _ __   __| |_| |_   ) / /_
 | '_ \ / _` | '_ \ / _` | | __| / / '_ \
 | |_) | (_| | | | | (_| | | |_ / /| (_) |
--More--(83%) 
v
 | |                   | (_) | |__ \ / /
 | |__   __ _ _ __   __| |_| |_   ) / /_
 | '_ \ / _` | '_ \ / _` | | __| / / '_ \
 | |_) | (_| | | | | (_| | | |_ / /| (_) |
"~/text.txt" [readonly] 6L, 258B 
:e /etc/bandit_pass/bandit26 
c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1 ~                                                                                                                            ~                                                                                                                            ~                                                                                                                            ~                                                                                                                            "/etc/bandit_pass/bandit26" [readonly] 1L, 33B 
:!q
 | |                   | (_) | |__ \ / /
 | |__   __ _ _ __   __| |_| |_   ) / /_
 | '_ \ / _` | '_ \ / _` | | __| / / '_ \
 | |_) | (_| | | | | (_| | | |_ / /| (_) |
Press ENTER or type command to continue q ~                                                                                                                            ~                                                                                                                            -----------------------Connection to localhost closed. bandit25@bandit:~ exit

## Notas opcionales.

Accedemos al nivel 25 de la forma habitual, estando en este nivel, ahora se ingresa al nivel 26 usando la llave ssh para este nivel y para poder ver la contraseña de bandit26 hay que hacer pequeña la ventana de comandos para que el ASCII art no cargue completamente. Después podemos pedir la contraseña con el comando cat.

## Referencias.

https://overthewire.org/wargames/bandit/bandit26.html
https://ingsoftware.reduaz.mx/moodle/mod/resource/view.php?id=36056