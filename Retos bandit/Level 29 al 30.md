# Level 29 al 30

## Objetivo.

Hay un repositorio de git en ssh://bandit29-git@localhost/home/bandit29-git/repo. La contraseña para el usuario bandit29-git es la misma que para el usuario bandit29.

Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso al nivel.

bandit29
tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

## Solución.

bandit29@bandit:~$ mktemp -d
/tmp/tmp.5fXimVYant
bandit29@bandit:~$ cd /tmp/tmp.5fXimVYant
bandit29@bandit:/tmp/tmp.5fXimVYant$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit29-git@localhost's password:
Permission denied, please try again.
bandit29-git@localhost's password:
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (16/16), done.
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/tmp.5fXimVYant$ ls
repo
bandit29@bandit:/tmp/tmp.5fXimVYant$ cd repo/
bandit29@bandit:/tmp/tmp.5fXimVYant/repo$ ls -la
total 16
drwxrwxr-x 3 bandit29 bandit29 4096 Mar  6 03:27 .
drwx------ 3 bandit29 bandit29 4096 Mar  6 03:27 ..
drwxrwxr-x 8 bandit29 bandit29 4096 Mar  6 03:27 .git
-rw-rw-r-- 1 bandit29 bandit29  131 Mar  6 03:27 README.md
bandit29@bandit:/tmp/tmp.5fXimVYant/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/tmp.5fXimVYant/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
bandit29@bandit:/tmp/tmp.5fXimVYant/repo$ git checkout dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/tmp.5fXimVYant/repo$ ls -la
total 20
drwxrwxr-x 4 bandit29 bandit29 4096 Mar  6 03:29 .
drwx------ 3 bandit29 bandit29 4096 Mar  6 03:27 ..
drwxrwxr-x 2 bandit29 bandit29 4096 Mar  6 03:29 code
drwxrwxr-x 8 bandit29 bandit29 4096 Mar  6 03:29 .git
-rw-rw-r-- 1 bandit29 bandit29  134 Mar  6 03:29 README.md
bandit29@bandit:/tmp/tmp.5fXimVYant/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

## Notas opcionales.

La ramificación de Git es otra característica del sistema de control de versiones. Te permite dividir el desarrollo en diferentes ramas. Específicamente, hay una rama maestra de la que se puede tomar el software y se puede trabajar en él por separado. Puede cambiar y agregar funciones mientras mantiene una rama principal en funcionamiento. Una vez realizado el trabajo, se puede integrar de nuevo en la rama maestra. Esto permite un control de versión adicional. Puede ofrecer una rama de producción con software utilizable, mientras corrige errores o agrega funciones en una rama de desarrollo diferente.

Los comandos básicos para trabajar con ramas son:

git branch: enumera (-a), crea o elimina ramas
git checkout <branch_name>/git switch <branch_name>: cambiar de sucursal
git merge: unir dos o más ramas

## Referencias.

https://overthewire.org/wargames/bandit/bandit30.html
https://mayadevbe.me/posts/overthewire/bandit/level30/
