
# Level 6 al 7

## Objetivo.

La contraseña del siguiente nivel está alamcenada en **somewhere on the server** y posee las siguientes propiedades:

-   propiedad del usuario bandit7
-   propiedad del grupo bandit6
-   33 bytes de tamaño

## Datos de acceso al nivel.

bandit6
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

## Solución.

bandit6@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Jan 11 19:18 .
drwxr-xr-x 70 root root 4096 Jan 11 19:19 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit6@bandit:~$ find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
/var/lib/dpkg/info/bandit7.password
-bash: /var/lib/dpkg/info/bandit7.password: Permission denied
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## Notas opcionales.

Usamos el comando `find` con las siguientes opciones:

-   `-type f`, porque estamos buscando un archivo.
-   `-user bandit7`, para buscar los archivos propedad del usuario bandit7
-   `-group bandit6`, tpara buscar los archivos propedad del grupo bandit6
-   `-size 33c`, para buscar todos los archivos con tamaño de 33 bytes

Podemos correr el comando desde el directorio raíz para buscar en todo el sistema. Ejecutando el comando `find / -type f -user bandit7 -group bandit6 -size 33c` sin embargo, también se mostrará un mensaje de error: `Permission denied` para los archivos para los que no tenemos permiso. Añadimos `2>/dev/null`, el cual ‘muestra’ todos los mensajes de error.

## Referencias.

https://overthewire.org/wargames/bandit/bandit7.html
https://mayadevbe.me/posts/overthewire/bandit/level7/
https://stackoverflow.com/questions/762348/how-can-i-exclude-all-permission-denied-messages-from-find
