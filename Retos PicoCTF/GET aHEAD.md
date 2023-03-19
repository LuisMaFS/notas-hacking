# GET aHEAD

## Objetivo.

Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:15931/](http://mercury.picoctf.net:15931/)

## Solución.

frausto_san-picoctf@webshell:~$ curl -x HEAD http://mercury.picoctf.net:15931/index.php
curl: (5) Could not resolve proxy: HEAD
frausto_san-picoctf@webshell:~$ curl -I HEAD http://mercury.picoctf.net:15931/index.php
curl: (6) Could not resolve host: HEAD
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_82880908}
Content-type: text/html; charset=UTF-8

## Notas opcionales.

**¿Qué es el comando CURL?**
Curl es una herramienta de línea de comandos de Linux que sirve para transferir datos hacia o desde un servidor con URL, utilizando cualquiera de los protocolos soportados (HTTP, FTP, POP3, IMAP, SMTP, SCP, SFTP, TFTP, TELNET, LDAP…).

## Referencias.

https://www.hostgator.mx/blog/comando-curl-linux/#:~:text=%C2%BFQu%C3%A9%20es%20el%20comando%20curl,%2C%20TELNET%2C%20LDAP%E2%80%A6).