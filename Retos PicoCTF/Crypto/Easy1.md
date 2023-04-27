
# Easy1

## Objetivo.

The one time pad can be cryptographically secure, but not when you know the key. Can you solve this? We've given you the encrypted flag, key, and a table to help `UFJKXQZQUNB` with the key of `SOLVECRYPTO`. Can you use this [table](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) to solve it?.

## Solución.

**Descargar el archivo para el reto**

┌──(kali㉿kali)-[~/picoctf/crypto/easy1]

└─$ wget https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt

**Abrimos el archivo txt**

┌──(kali㉿kali)-[~/picoctf/crypto/easy1]

└─$ open table.txt    

con la llave proporcionada SOLVECRYPTO y el cifrado UFJKXQZQUNB obtenemos en texto plano la bandera CRYPTOISFUN
picoCTF{UFJKXQZQUNB}

## Notas opcionales.


**Cifrado Vigènere**

El cifrado Vigenère es un cifrado basado en diferentes series de caracteres o letras del cifrado César formando estos caracteres una tabla, llamada tabla de Vigenère, que se usa como clave. El cifrado de Vigenère es un cifrado polialfabético y de sustitución.

El cifrado Vigenère se ha reinventado muchas veces. El método original fue descrito por Giovan Batista Belaso en su libro de 1553 "_La cifra del Sig. Giovan Batista Belaso"_, quien construyó el cifrado basándose en la tabula recta de Trithemius, pero añadió una clave repetida para cambiar cada carácter entre los diferentes alfabetos. Sin embargo, fue incorrectamente atribuido en el siglo XIX a Blaise de Vigenère, a partir de un trabajo realizado en 1583, y por ello aún se le conoce como el "_cifrado Vigenère_".

## Referencias.

https://www.ugr.es/~anillos/textos/pdf/2011/EXPO-1.Criptografia/02a11.htm#:~:text=El%20cifrado%20Vigen%C3%A8re%20es%20un,se%20ha%20reinventado%20muchas%20veces.

Vídeo

https://www.youtube.com/watch?v=ww1xjGR2C6w&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=35&ab_channel=hackadvisermx
