# Level 31 al 32

## Objetivo.

Hay un repositorio de git en ssh://bandit31-git@localhost/home/bandit31-git/repo. La contraseña para el usuario bandit31-git es la misma que para el usuario bandit31.

Clona el repositorio y encuentra la contraseña para el siguiente nivel.

## Datos de acceso al nivel.

bandit31
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

## Solución.

bandit31@bandit:~$ mktemp -d
/tmp/tmp.qm4jOiWXzS
bandit31@bandit:~$ cd /tmp/tmp.qm4jOiWXzS
bandit31@bandit:/tmp/tmp.qm4jOiWXzS$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes

bandit31-git@localhost's password:
Permission denied, please try again.
bandit31-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), 382 bytes | 382.00 KiB/s, done.
bandit31@bandit:/tmp/tmp.qm4jOiWXzS$ ls
repo
bandit31@bandit:/tmp/tmp.qm4jOiWXzS$ cd repo
bandit31@bandit:/tmp/tmp.qm4jOiWXzS/repo$ ls
README.md
bandit31@bandit:/tmp/tmp.qm4jOiWXzS/repo$ cat README.md
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

bandit31@bandit:/tmp/tmp.qm4jOiWXzS/repo$ git branch
* master
bandit31@bandit:/tmp/tmp.qm4jOiWXzS/repo$ touch key.txt
bandit31@bandit:/tmp/tmp.qm4jOiWXzS/repo$ echo "May I come in?" > key.txt
bandit31@bandit:/tmp/tmp.qm4jOiWXzS/repo$ git add key.txt
The following paths are ignored by one of your .gitignore files:
key.txt
hint: Use -f if you really want to add them.
hint: Turn this message off by running
hint: "git config advice.addIgnoredFile false"
bandit31@bandit:/tmp/tmp.qm4jOiWXzS/repo$ ls -al
total 24
drwxrwxr-x 3 bandit31 bandit31 4096 Mar  6 03:58 .
drwx------ 3 bandit31 bandit31 4096 Mar  6 03:57 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Mar  6 03:58 .git
-rw-rw-r-- 1 bandit31 bandit31    6 Mar  6 03:57 .gitignore
-rw-rw-r-- 1 bandit31 bandit31   15 Mar  6 03:58 key.txt
-rw-rw-r-- 1 bandit31 bandit31  147 Mar  6 03:57 README.md
bandit31@bandit:/tmp/tmp.qm4jOiWXzS/repo$ cat .gitignore
*.txt
bandit31@bandit:/tmp/tmp.qm4jOiWXzS/repo$ rm .gitignore
bandit31@bandit:/tmp/tmp.qm4jOiWXzS/repo$ git add key.txt
bandit31@bandit:/tmp/tmp.qm4jOiWXzS/repo$ git commit -m "Upload a file"
[master d344a13] Upload a file
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt
bandit31@bandit:/tmp/tmp.qm4jOiWXzS/repo$ git push origin master
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).

bandit31-git@localhost's password:
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 326 bytes | 326.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
remote: Well done! Here is the password for the next level:
remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'

## Notas opcionales.

Git Commit guarda los cambios realizados actualmente con un mensaje que describe estos cambios. El indicador -a se asegura de que todos los archivos modificados/eliminados estén preparados.

Git Push actualiza los cambios locales en repositorios remotos. Al presionar por primera vez, también debe definir la rama con -u.

Git Ignore es un archivo con el nombre de archivo '.gitignore'. En este archivo, se escriben todos los nombres/extensiones de archivos que deben ser ignorados por la confirmación. Esto significa que si se crea/modifica un archivo que está en el archivo ignorado, no formará parte de la confirmación/repositorio. Git ignore también permite comodines. (Por ejemplo: '*.pyc' significa que se ignorarán todos los archivos con la terminación '.pyc'). Hay archivos preescritos para situaciones e idiomas específicos, como este para Python.

Git Add actualiza qué archivos formarán parte de la próxima confirmación. El indicador -f obliga a que los archivos puedan confirmarse, incluso cuando normalmente se ignoran.

## Referencias.

https://overthewire.org/wargames/bandit/bandit32.html
https://mayadevbe.me/posts/overthewire/bandit/level32/