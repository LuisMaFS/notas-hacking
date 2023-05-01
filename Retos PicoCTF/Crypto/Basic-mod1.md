# Basic-mod1

## Objetivo.

We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/129/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

## Solución.

**Descargar el archivo de texto para el reto**

┌──(kali㉿kali)-[~/picoctf/crypto/basicmod1]

└─$ wget https://artifacts.picoctf.net/c/129/message.txt  
**Con un script de python podremos obtener la bandera de acuerdo a las pistas que nos da la descripción del reto**

┌──(kali㉿kali)-[~/picoctf/crypto/basicmod1]

└─$ nano exp.py 
```
datos = open('message.txt').read().split()

print(datos)

flag = ''

for n in datos:
        c = int(n) % 37
        if c>=0 and c<=25:
                s = chr(c+65)
        elif c>=26 and c<=35:
                s = chr(c+22)
        else:
                s = '_'
        flag += s

print(f"picoCTF{{{flag}}}")

```

**Si ejecutamos el programa obtendremos la bandera**

┌──(kali㉿kali)-[~/picoctf/crypto/basicmod1]

└─$ python3 exp.py

['350', '63', '353', '198', '114', '369', '346', '184', '202', '322', '94', '235', '114', '110', '185', '188', '225', '212', '366', '374', '261', '213']

picoCTF{R0UND_N_R0UND_ADD17EC2}

## Notas opcionales.

## Referencias.

**Vídeo**

https://www.youtube.com/watch?v=t3vRV-j0mF0&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=46&ab_channel=hackadvisermx