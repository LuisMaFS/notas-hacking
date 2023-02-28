# Level 20 al 21

## Objetivo.

Hay un binario setuid en el directorio de inicio que hace lo siguiente: establece una conexión con localhost en el puerto que especifique como argumento de la línea de comandos. Luego lee una línea de texto de la conexión y la compara con la contraseña del nivel anterior (bandit20). Si la contraseña es correcta, transmitirá la contraseña para el siguiente nivel (bandit21).

NOTA: intente conectarse a su propio demonio de red para ver si funciona como cree

## Datos de acceso al nivel.

bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT

## Solución.

bandit20@bandit:~$ echo -n 'VxCazJaVykI6W36BkBU0mJTCM8rR95XT' | nc -l -p 1234 &
[2] 1005097
[1]   Done                    echo -n 'GbKksEFF4yrVs6il55v6gwY5aVje5f0j' | nc -l -p 1234
bandit20@bandit:~$ ./suconnect 1234
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

## Notas opcionales.

1. Usando 'netcat', podemos crear una conexión en modo servidor, que escucha la conexión entrante. Para que netcat envíe la contraseña, uso echo y la canalizo a netcat. El indicador -n es para evitar caracteres de nueva línea en la entrada. Por último, dejamos que el proceso se ejecute en segundo plano con &.

2. Ejecutar el binario setuid con el puerto 1234 significa que se conectará a nuestro servidor netcat, recibirá la contraseña ingresada a través de echo y enviará la siguiente contraseña.

## Referencias.

https://overthewire.org/wargames/bandit/bandit21.html
https://mayadevbe.me/posts/overthewire/bandit/level21/