# 14-Permissions

## Objetivo.

Can you read files in the root file?

Additional details will be available after launching your challenge instance.

**Datos de acceso**

**Conección a ete servidor por medio de SSH:** <font color="orange">ssh -p 60484 picoplayer@saturn.picoctf.net</font>
**Password:** <font color="orange">a2XEKFgg3l</font>

## Solución.

**Ingresar a la carpeta /**
picoplayer@challenge:~$ cd /

**Revisar el contenido, dentro del directorio /, hay más subcarpetas, entremos a la subcarpeta challenge**
picoplayer@challenge:/$ ls
bin   <font color="red">challenge</font>  etc   lib    lib64   media  opt   root  sbin  sys  usr
boot  dev        home  lib32  libx32  mnt    proc  run   srv   tmp  var

picoplayer@challenge:/$ cd challenge/

**Una vez dentro de la subcarpeta, revisamos su contenido, esta contiene un archivo json, llamado metadata.json**
picoplayer@challenge:/challenge$ ls
metadata.json

**Con el comando <font color="red">cat</font>, podemos ver el contenido de un archivo existente**
**Podemos ver que el archivo contiene la bandera para el reto**
picoplayer@challenge:/challenge$ cat metadata.json 
{"flag": "<font color="cyan">picoCTF{uS1ng_v1m_3dit0r_1cee9dcb}</font>", "username": "picoplayer", "password": "a2XEKFgg3l"}picoplayer@challenge:/challenge$ 

## Notas opcionales.

## Referencias.