# Strings it

## Objetivo.

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?

## Solución.

frausto_san-picoctf@webshell:~$ strings strings -a | grep 'pico'
picoCTF{5tRIng5_1T_7f766a23}

## Notas opcionales.

Abrimos webshell de picoCTF.
Aquí usamos el comando wget y pegamos el link del archivo strings que nos proporciona el reto.
escribimos el siguientr comando y obtenemos la bandera

## Referencias.