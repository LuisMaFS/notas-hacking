# Level 16 al 17

## Objetivo.

Las credenciales para el siguiente nivel se pueden recuperar enviando la contraseña del nivel actual a un puerto en localhost en el rango de 31000 a 32000. Primero averigüe cuál de estos puertos tiene un servidor escuchando en ellos. Luego, averigüe cuáles de ellos hablan SSL y cuáles no. Solo hay 1 servidor que proporcionará las siguientes credenciales, los demás simplemente le enviarán lo que le envíe.

## Datos de acceso al nivel.

bandit16
JQttfApK4SeyHwDlI9SXGR50qclOAil1

## Solución.

bandit16@bandit:~$ nmap -p 31000-32000 127.0.0.1
Starting Nmap 7.80 ( https://nmap.org ) at 2023-02-27 00:22 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.000098s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.05 seconds
bandit16@bandit:~$ nmap -p 31046.31518,31691,31790,31960 -A localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2023-02-27 00:24 UTC
Error #487: Your port specifications are illegal.  Example of proper form: "-100,200-1024,T:3000-4000,U:60000-"
QUITTING!
bandit16@bandit:~$ nmap -p 31046,31518,31691,31790,31960 -A localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2023-02-27 00:24 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00011s latency).

PORT      STATE SERVICE     VERSION
31046/tcp open  echo
31518/tcp open  ssl/echo
| ssl-cert: Subject: commonName=localhost
| Subject Alternative Name: DNS:localhost
| Not valid before: 2023-02-24T22:58:04
|_Not valid after:  2023-02-24T22:59:04
31691/tcp open  echo
31790/tcp open  ssl/unknown
| fingerprint-strings:
|   FourOhFourRequest, GenericLines, GetRequest, HTTPOptions, Help, Kerberos, LDAPSearchReq, LPDString, RTSPRequest, SIPOptions, SSLSessionReq, TLSSessionReq, TerminalServerCookie:
|_    Wrong! Please enter the correct current password
| ssl-cert: Subject: commonName=localhost
| Subject Alternative Name: DNS:localhost
| Not valid before: 2023-02-24T22:58:05
|_Not valid after:  2023-02-24T22:59:05
31960/tcp open  echo
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
SF-Port31790-TCP:V=7.80%T=SSL%I=7%D=2/27%Time=63FBF844%P=x86_64-pc-linux-g
SF:nu%r(GenericLines,31,"Wrong!\x20Please\x20enter\x20the\x20correct\x20cu
SF:rrent\x20password\n")%r(GetRequest,31,"Wrong!\x20Please\x20enter\x20the
SF:\x20correct\x20current\x20password\n")%r(HTTPOptions,31,"Wrong!\x20Plea
SF:se\x20enter\x20the\x20correct\x20current\x20password\n")%r(RTSPRequest,
SF:31,"Wrong!\x20Please\x20enter\x20the\x20correct\x20current\x20password\
SF:n")%r(Help,31,"Wrong!\x20Please\x20enter\x20the\x20correct\x20current\x
SF:20password\n")%r(SSLSessionReq,31,"Wrong!\x20Please\x20enter\x20the\x20
SF:correct\x20current\x20password\n")%r(TerminalServerCookie,31,"Wrong!\x2
SF:0Please\x20enter\x20the\x20correct\x20current\x20password\n")%r(TLSSess
SF:ionReq,31,"Wrong!\x20Please\x20enter\x20the\x20correct\x20current\x20pa
SF:ssword\n")%r(Kerberos,31,"Wrong!\x20Please\x20enter\x20the\x20correct\x
SF:20current\x20password\n")%r(FourOhFourRequest,31,"Wrong!\x20Please\x20e
SF:nter\x20the\x20correct\x20current\x20password\n")%r(LPDString,31,"Wrong
SF:!\x20Please\x20enter\x20the\x20correct\x20current\x20password\n")%r(LDA
SF:PSearchReq,31,"Wrong!\x20Please\x20enter\x20the\x20correct\x20current\x
SF:20password\n")%r(SIPOptions,31,"Wrong!\x20Please\x20enter\x20the\x20cor
SF:rect\x20current\x20password\n");

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 98.55 seconds
bandit16@bandit:~$ cat /etc/bandit_pass/bandit16
JQttfApK4SeyHwDlI9SXGR50qclOAil1

bandit17@bandit:~$ whoami
bandit17
bandit17@bandit:~$ cat /etc/bandit_pass/bandit17
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e

## Notas opcionales.

NMAP es un escáner de red. Puede hacer descubrimiento de host, escaneo de puertos, detección de versiones (detección de servicios) y mucho más. Para esta tarea, el indicador -p es importante. Esta bandera nos permite elegir qué puertos escanear. Por defecto, NMAP escanea los 1000 puertos principales (no los primeros 1000 puertos). Use -P- para escanear todos los puertos 65535. La bandera -sv nos permite hacer un escaneo de detección de servicio/versión. Es posible hacer que NMAP realice todos los escaneos posibles con la bandera -A

## Referencias. 

https://overthewire.org/wargames/bandit/bandit17.html
https://mayadevbe.me/posts/overthewire/bandit/level17/