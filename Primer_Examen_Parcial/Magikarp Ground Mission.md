# Magikarp Ground Mission

## Objetivo.

Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `481e7b14`

Additional details will be available after launching your challenge instance.

## Solución.

**Usando el shell de picoCTF, nos conectamos usando ssh a la direcciónctf-player@venus.picoctf.net usando el puerto 51271**
ssh ctf-player@venus.picoctf.net -p 51271

**Nos el shell pedirá una contraseña**
La cual es **481e7b14**

**Dentro del shell, escribimos el comando ls, para ver el contenido del directorio**
ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
**Se observa que hay dos archivos**

**Ejecutamos el comando more para ver más información del archivo 1of3.flag.txt**
ctf-player@pico-chall$ more 1of3.flag.txt 
picoCTF{xxsh_
**Nos da una parte de la bandera**

**Ejecutamos el comando more para ver más información del archivo instructions-to-2of3.txt**
ctf-player@pico-chall$ more instructions-to-2of3.txt 
Next, go to the root of all things, more succinctly `/`
**Nos da una pista para encontrar la siguiente parte de la bandera**

**Nos dirigimos al directorio raíz**
ctf-player@pico-chall$ 
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls
ctf-player
ctf-player@pico-chall$ cd /  
ctf-player@pico-chall$ ls -la
total 92
drwxr-xr-x   1 root root 4096 Mar 21 01:45 .
drwxr-xr-x   1 root root 4096 Mar 21 01:45 ..
-rwxr-xr-x   1 root root    0 Mar 21 01:45 .dockerenv
-rw-r--r--   1 root root   17 Mar 16  2021 2of3.flag.txt
drwxr-xr-x   1 root root 4096 Mar 16  2021 bin
drwxr-xr-x   2 root root 4096 Apr 24  2018 boot
drwxr-xr-x   5 root root  340 Mar 21 01:45 dev
drwxr-xr-x   1 root root 4096 Mar 21 01:45 etc
drwxr-xr-x   1 root root 4096 Mar 16  2021 home
-rw-r--r--   1 root root   51 Mar 16  2021 instructions-to-3of3.txt
drwxr-xr-x   1 root root 4096 Mar 16  2021 lib
drwxr-xr-x   2 root root 4096 Feb 22  2021 lib64
drwxr-xr-x   2 root root 4096 Feb 22  2021 media
drwxr-xr-x   2 root root 4096 Feb 22  2021 mnt
drwxr-xr-x   1 root root 4096 Mar 16  2021 opt
dr-xr-xr-x 210 root root    0 Mar 21 01:45 proc
drwx------   2 root root 4096 Feb 22  2021 root
drwxr-xr-x   1 root root 4096 Mar 21 01:48 run
drwxr-xr-x   1 root root 4096 Mar 16  2021 sbin
drwxr-xr-x   2 root root 4096 Feb 22  2021 srv
dr-xr-xr-x  13 root root    0 Mar 21 01:45 sys
drwxrwxrwt   1 root root 4096 Mar 16  2021 tmp
drwxr-xr-x   1 root root 4096 Feb 22  2021 usr
drwxr-xr-x   1 root root 4096 Feb 22  2021 var
ctf-player@pico-chall$ more root

*** root: directory ***

**Ejecutamos el comando more para ver más información del archivo 2of3.flag.txt**
ctf-player@pico-chall$ more 2of3.flag.txt 
0ut_0f_VV4t3r_
**Obtenemos la segunda parte de la bandera**

**Ejecutamos el comando more para ver más información del archivo instructions-to-3of3.txt**
ctf-player@pico-chall$ more instructions-to-3of3.txt 
Lastly, ctf-player, go home... more succinctly `~`
**Nos da una pista para encontrar la siguiente parte de la bandera*

**Nos dirigimos al directorio home con ~**
ctf-player@pico-chall$ cd ~
ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
**Hay dos archivos**

**Ejecutamos el comando more para ver más información del archivo 3of3.flag.txt**
ctf-player@pico-chall$ more 3of3.flag.txt 
1118a9a4}
**Obtenemos la parte final de la bandera**

**Juntamos los fragmentos**
picoCTF{xxsh_0ut_0f_VV4t3r_1118a9a4}

## Notas opcionales.

## Referencias.

https://www.youtube.com/watch?v=vgot6wfqPqo&ab_channel=JByrne