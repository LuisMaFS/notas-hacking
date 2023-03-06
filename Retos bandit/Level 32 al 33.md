# Level 32 al 33

## Objetivo.

Después de todo esto, es hora de otro escape. ¡Buena suerte!

## Datos de acceso al nivel.

bandit32
rmCBvG56y58BXzv98yZGdO7ATVL5dW8y

## Solución.

WELCOME TO THE UPPERCASE SHELL
>>ls
sh: 1: LS: not found
>> $0
$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Feb 21 22:03 .
drwxr-xr-x 70 root     root      4096 Feb 21 22:04 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit33 bandit32 15128 Feb 21 22:03 uppershell
$ whoami
bandit33
$ cat /etc/bandit\_pass/bandit33
odHo63fHiFqcWWJG9rLiLDtPm45KzUKy

## Notas opcionales.

Comandos del SHELL
TERM: emulación de terminal actual
HOME: la ruta al directorio de inicio del usuario actualmente conectado
LANG: configuración local actual
PATH: lista de directorios que se buscará al ejecutar comandos
PWD: nombre de ruta del directorio de trabajo actual
SHELL/0: la ruta del shell del usuario actual
USER: usuario conectado actualmente

Con $0 cambiamos el SHELL a que actue como Linux.

## Referencias.

https://overthewire.org/wargames/bandit/bandit33.html
https://mayadevbe.me/posts/overthewire/bandit/level33/