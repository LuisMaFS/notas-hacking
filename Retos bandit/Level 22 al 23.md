# Level 22 al 23

## Objetivo.

Un programa se ejecuta automáticamente a intervalos regulares desde cron, el programador de trabajos basado en el tiempo. Busque en /etc/cron.d/ la configuración y vea qué comando se está ejecutando.

NOTA: Mirar scripts de shell escritos por otras personas es una habilidad muy útil. El guión para este nivel se hace fácil de leer intencionalmente. Si tiene problemas para comprender lo que hace, intente ejecutarlo para ver la información de depuración que imprime.

## Datos de acceso al nivel.

bandit22
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

## Solución.

bandit22@bandit:~$ ls -la /etc/cron.d
total 56
drwxr-xr-x   2 root root  4096 Feb 21 22:04 .
drwxr-xr-x 108 root root 12288 Feb 21 22:04 ..
-rw-r--r--   1 root root    62 Feb 21 22:02 cronjob_bandit15_root
-rw-r--r--   1 root root    62 Feb 21 22:02 cronjob_bandit17_root
-rw-r--r--   1 root root   120 Feb 21 22:03 cronjob_bandit22
-rw-r--r--   1 root root   122 Feb 21 22:03 cronjob_bandit23
-rw-r--r--   1 root root   120 Feb 21 22:03 cronjob_bandit24
-rw-r--r--   1 root root    62 Feb 21 22:03 cronjob_bandit25_root
-rw-r--r--   1 root root   201 Jan  8  2022 e2scrub_all
-rwx------   1 root root    52 Feb 21 22:04 otw-tmp-dir
-rw-r--r--   1 root root   102 Mar 23  2022 .placeholder
-rw-r--r--   1 root root   396 Feb  2  2021 sysstat
bandit22@bandit:~$  cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ echo I am user bandit23 | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

## Notas opcionales.

Mirando el script ‘/usr/bin/cronjob_bandit23.sh’, la última línea es similar al nivel 22. Este script solo introduce variables. La primera variable es 'myname' y guarda la salida del comando whoami. Debido a que este script se ejecutará como bandit23, el comando whoami imprimirá 'bandit23'. Entonces, la última línea nos dice que la contraseña de bandit23 se escribirá en un archivo en la carpeta '/ tmp'. El nombre del archivo se crea con la línea echo I am user $myname | md5sum | cut -d ' ' -f 1. Solo necesitamos sustituir $myname por bandit23, ejecutarlo y el resultado es el nombre del archivo

## Referencias.

https://overthewire.org/wargames/bandit/bandit23.html
https://mayadevbe.me/posts/overthewire/bandit/level23/