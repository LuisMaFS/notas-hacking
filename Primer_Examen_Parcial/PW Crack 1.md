# PW Crack 1

## Objetivo.

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/10/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/10/level1.flag.txt.enc) in the same directory too.

## Solución.

**Descargar en el shell, los archivos necesarios para el reto**

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack1$ wget https://artifacts.picoctf.net/c/10/level1.py

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack1$ wget https://artifacts.picoctf.net/c/10/level1.flag.txt.enc

**Revisar si se descargaron correctamente**

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack1$ ls

level1.flag.txt.enc  level1.py

**Hacer CAT al programa python, este nos dará la contraseña requerida para obtener la bandera**

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack1$ cat level1.py

	def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "691d"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")


**La contraseña es 691d**

**Ejecutamos el programa y colocamos la contraseña requerida y obtenemos la bandera**

frausto_san-picoctf@webshell:~/picoctf/examen/pwcrack1$ python3 level1.py

Please enter correct password for flag: 691d

Welcome back... your flag, user:

picoCTF{545h_r1ng1ng_56891419}

## Notas opcionales.

## Referencias.

https://www.youtube.com/watch?v=hdtQHEFBQh0&ab_channel=AvinashSharma