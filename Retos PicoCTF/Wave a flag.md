# Wave a flag

## Objetivo.

Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm) has extraordinarily helpful information...

## Solución.

**Descargamos el  archivo que se requiere para este reto, en el webshell de picoCTF**
frausto_san-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm
...

**Buscamos el archivo en el directorio, el archivo se llama "warm"**
frausto_san-picoctf@webshell:~$ ls
README.txt  fg  flag  strings  strings.1  warm

**Ejecutamos el comando file, para comprobar de que tipo de archivo se trata, y el tipo de archivo es un ejecutable**
frausto_san-picoctf@webshell:~$ file warm
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=b11c22752c901adc13ba1ce86eda9d5516f22763, with debug_info, not stripped

**Escribimos la siguiente límea "./warm", la ventana de comando, nos regresa que no tenemos permiso para realizar la operación**
frausto_san-picoctf@webshell:~$ ./warm
-bash: ./warm: Permission denied
frausto_san-picoctf@webshell:~$ sudo ./warm
-bash: sudo: command not found

**Con el comando chmod, cambiamos de modo, para que nos otorguen permisos, con la extención "+x", establecemos la ejecución del archivo para todos los usuarios**
frausto_san-picoctf@webshell:~$ chmod +x warm

**En la siguiente ejecución nos regresa la bandera**
frausto_san-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_d6969390}

## Notas opcionales.

En este reto, aprendemos a usar el comando chmod, decubriendo que sí hay archivos que se necesitan permisos, cambiamos de modo con chmod, y con la extención "+x", ejecutamos el archivo para todos los usuarios.

## Referencias.

https://medium.com/@arthDetroja/picoctf-write-up-wave-a-flag-fc1f42dc5d4d