# Level 27 al 28

## Objetivo.

Hay un repositorio de git en ssh://bandit27-git@localhost/home/bandit27-git/repo. La contraseña para el usuario bandit27-git es la misma que para el usuario bandit27.

Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso al nivel.

bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

## Solución.

bandit27@bandit:~$ mktemp -d
/tmp/tmp.JxdoZyHKzO
bandit27@bandit:~$ cd /tmp/tmp.JxdoZyHKzO
bandit27@bandit:/tmp/tmp.JxdoZyHKzO$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit27-git@localhost's password:
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
bandit27@bandit:/tmp/tmp.JxdoZyHKzO$ ls -la
total 124
drwx------   3 bandit27 bandit27   4096 Mar  2 03:32 .
drwxrwx-wt 954 root     root     114688 Mar  2 03:32 ..
drwxrwxr-x   3 bandit27 bandit27   4096 Mar  2 03:32 repo
bandit27@bandit:/tmp/tmp.JxdoZyHKzO$ cd repo/
bandit27@bandit:/tmp/tmp.JxdoZyHKzO/repo$ ls
README
bandit27@bandit:/tmp/tmp.JxdoZyHKzO/repo$ cat README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR

## Notas opcionales.

Primero, creamos un directorio para el proyecto y luego lo clonamos.
Habrá una solicitud de contraseña. Simplemente escribimos la contraseña de Bandit 27 y el repositorio se clonará. 
Cuando podamos ver el contenido del repositorio, escribimos el comando Cat del archivo README para obtener la contraseña de bandit28

## Referencias.

https://overthewire.org/wargames/bandit/bandit28.html
https://ingsoftware.reduaz.mx/moodle/mod/resource/view.php?id=36056