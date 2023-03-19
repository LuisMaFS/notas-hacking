# Based

## Objetivo.

To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29956`.

## Solución.

El reto es contrareloj, entonces cuando ejecutamos el comando  nc jupiter.challenges.picoctf.org 29956, nos arrojará cifras en distintas bases que tenemos que convertirlas a palabras para obtener la bandera

frausto_san-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 29956
Let us see how data is stored
pie
Please give the 01110000 01101001 01100101 as a word.
...
you have 45 seconds.....

Input:
pie
Please give me the  154 151 172 141 162 144 as a word.
Input:
lizard
Please give me the 6c696d65 as a word.
Input:
lime
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_b375bb16}

## Notas opcionales.

Para realizar el reto me base en la página rapitables, ya que esta plataforma permite convertir números de distintas bases a palabras o código ASCII.

## Referencias.

http://www.unit-conversion.info/texttools/octal/
https://www.rapidtables.com/convert/number/ascii-hex-bin-dec-converter.html
https://www.rapidtables.com/convert/number/binary-to-ascii.html