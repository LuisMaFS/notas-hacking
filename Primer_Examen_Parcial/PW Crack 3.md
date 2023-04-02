# PW Crack 3

## Objetivo.

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/16/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/16/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/16/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Solución.

**Descargar en el shell, los archivos necesarios para el reto**

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack3$ wget https://artifacts.picoctf.net/c/16/level3.py

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack3$ wget https://artifacts.picoctf.net/c/16/level3.hash.bin

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack3$ wget https://artifacts.picoctf.net/c/16/level3.flag.txt.enc

**Revisar si se descargaron correctamente**

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack3$ ls

level3.flag.txt.enc  level3.hash.bin  level3.py

**Hacer CAT al programa python, este nos dará la contraseña requerida para obtener la bandera**

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack3$ cat level3.py

**Nos fijamos en la parte de abajo**

**#**  The strings below are 7 possibilities for the correct password. 

**#**  (Only 1 is correct)

pos_pw_list = ["6997", "3ac8", "f0ac", "4b17", "ec27", "4e66", "865e"]

**Cualquiera de esos números es la contraseña**

**Probemos**

**Ejecutamos el programa, para obtener la bandera**

** La contraseña fue 865e**

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack3$ python3 level3.py

Please enter correct password for flag: 865e

Welcome back... your flag, user:

picoCTF{m45h_fl1ng1ng_2b072a90}

## Notas opcionales.

## Referencias.

https://www.youtube.com/watch?v=QLUZtEX8-ug&ab_channel=number0x01