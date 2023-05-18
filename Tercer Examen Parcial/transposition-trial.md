# transposition-trial

## Objetivo.

Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message.Download the corrupted message [here](https://artifacts.picoctf.net/c/192/message.txt).

## Solución.

**Descargar el archivo del reto**

┌──(kali㉿kali)-[~/picoctf/tercerparcial/transpositiontrial]

└─$ wget https://artifacts.picoctf.net/c/192/message.txt

**Abrimos el archivo**

┌──(kali㉿kali)-[~/picoctf/tercerparcial/transpositiontrial]

└─$ cat message.txt
```
heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V091B0AE}2
```

Con el sguiente script podremos obtener la bandera

```
ctxt = "heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V091B0AE}2"
ptxt = ""
 
for i in range(len(ctxt)):
    if i % 3 == 0:
        ptxt = ptxt + ctxt[i+2] + ctxt[i]
    elif i % 3 == 2:
        pass
    else:
        ptxt = ptxt + ctxt[i]
 
print(ptxt)
```

**Bandera** picoCTF{7R4N5P051N6_15_3XP3N51V3_109AB02E}

## Notas opcionales.

## Referencias.

https://dlsblog.com/2022/04/09/picoctf-2022-transposition-trial-write-up/