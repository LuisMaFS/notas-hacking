# PW Crack 2

## Objetivo.

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/15/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/15/level2.flag.txt.enc) in the same directory too.

## Solución.

**Descargar en el shell, los archivos necesarios para el reto**

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack2$ wget https://artifacts.picoctf.net/c/15/level2.py

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack2$ wget https://artifacts.picoctf.net/c/15/level2.flag.txt.enc

**Revisar si se descargaron correctamente**

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack2$ ls

level2.flag.txt.enc  level2.py

**Hacer CAT al programa python, este nos dará la contraseña requerida para obtener la bandera**

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack2$ cat level2.py

	def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")


**La contraseña es chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65)**

**Usaremos python para saber que significa la contraseña**

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack2$ python3 

Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux

Type "help", "copyright", "credits" or "license" for more information.

**>>>** chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65)

'39ce'

**La contaseña es 39ce**

**Ejecutamos el programa, para obtener la bandera**

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack2$ python3 level2.py 

Please enter correct password for flag: 39ce

Welcome back... your flag, user:

picoCTF{tr45h_51ng1ng_502ec42e}

## Notas opcionales.

## Referencias.

https://www.youtube.com/watch?v=IHErfWAqliM&ab_channel=AvinashSharma