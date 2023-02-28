# Level 15 al 16

## Objetivo.

La contraseña para el siguiente nivel se puede recuperar enviando la contraseña del nivel actual al puerto 30001 en localhost usando encriptación SSL.

Nota útil: ¿Obtienes "HEARTBEATING" y "Read R BLOCK"? Use -ign_eof y lea la sección "CONNECTED COMMANDS" en la página de manual. Junto a 'R' y 'Q', el comando 'B' también funciona en esta versión de ese comando...

## Datos de acceso al nivel.

bandit15
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Solución.

bandit15@bandit:~$ openssl s_client -connect localhost:30001

Wrong! Please enter the correct current password
closed

bandit15@bandit:~$ cat /etc/bandit_pass/bandit15
JQttfApK4SeyHwDlI9SXGR50qclOAil1

## Notas opcionales.

OpenSSL es una biblioteca para la comunicación segura a través de redes. Implementa los protocolos criptográficos Transport Layer Security (TLS) y Secure Sockets Layer (SSL) que se utilizan, por ejemplo, en HTTPS para proteger el tráfico web.

openssl s_client es la implementación de un cliente simple que se conecta a un servidor mediante SSL/TLS.

## Referencias.

https://overthewire.org/wargames/bandit/bandit16.html
https://david-varghese.medium.com/overthewire-bandit-level-15-level-16-aea1b72721b0
https://mayadevbe.me/posts/overthewire/bandit/level16/