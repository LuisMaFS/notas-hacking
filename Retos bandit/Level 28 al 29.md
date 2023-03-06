# Level 28 al 29

## Objetivo.

Hay un repositorio de git en ssh://bandit28-git@localhost/home/bandit28-git/repo. La contraseña para el usuario bandit28-git es la misma que para el usuario bandit28.

Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso al nivel.

bandit28
AVanL161y9rsbcJIsFHuw35rjaOM19nR

## Solución.

bandit28@bandit:~$  mktemp -d
/tmp/tmp.goszaLUzVs
bandit28@bandit:~$ cd /tmp/tmp.goszaLUzVs
bandit28@bandit:/tmp/tmp.goszaLUzVs$  git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit28/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit28/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit28-git@localhost's password:
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 9 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (9/9), done.
Resolving deltas: 100% (2/2), done.
bandit28@bandit:/tmp/tmp.goszaLUzVs$ ls
repo
bandit28@bandit:/tmp/tmp.goszaLUzVs$ cd repo/
bandit28@bandit:/tmp/tmp.goszaLUzVs/repo$ ls -la
total 16
drwxrwxr-x 3 bandit28 bandit28 4096 Mar  6 03:11 .
drwx------ 3 bandit28 bandit28 4096 Mar  6 03:11 ..
drwxrwxr-x 8 bandit28 bandit28 4096 Mar  6 03:11 .git
-rw-rw-r-- 1 bandit28 bandit28  111 Mar  6 03:11 README.md
bandit28@bandit:/tmp/tmp.goszaLUzVs/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/tmp.goszaLUzVs/repo$ git log
commit 104db85a904e9691ff22aafe1a96124c88f75afa (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Tue Feb 21 22:03:10 2023 +0000

    fix info leak

commit 6c3c5e485cc531e5d52c321587ce1103833ab7c3
Author: Morla Porla <morla@overthewire.org>
Date:   Tue Feb 21 22:03:10 2023 +0000

    add missing data

commit cd3b97ef95879ec34df0d6c82f2a96d552f0e56c
Author: Ben Dover <noone@overthewire.org>
Date:   Tue Feb 21 22:03:10 2023 +0000

    initial commit of README.md

git show 6c3c5e485cc531e5d52c321587ce1103833ab7c3
commit 6c3c5e485cc531e5d52c321587ce1103833ab7c3
Author: Morla Porla <morla@overthewire.org>
Date:   Tue Feb 21 22:03:10 2023 +0000

    add missing data

diff --git a/README.md b/README.md
index 7ba2d2f..b302105 100644

--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
credentials

username: bandit29
password: TBD
password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

## Notas opcionales.

Fue similar al nivel anterior, pero la variación fue que el archivo README.md no devolvió la contraseña para el siguiente nivel.

git log: nos muestra el registro de confirmación.
git show (commit): nos muestra el contenido de una confirmación (al crear un repositorio público, es importante tener en cuenta la información que le envía, ya que se guardan los cambios y las versiones anteriores. Por lo tanto, los datos confidenciales, como las contraseñas, aún podrían ser recuperado).

## Referencias.

https://overthewire.org/wargames/bandit/bandit29.html
https://mayadevbe.me/posts/overthewire/bandit/level29/