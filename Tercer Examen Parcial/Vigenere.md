# Vigenere

## Objetivo.

Can you decrypt this message?Decrypt this [message](https://artifacts.picoctf.net/c/159/cipher.txt) using this key "CYLAB".

## Solución.

**Descargar el archivo del reto**

┌──(kali㉿kali)-[~/picoctf/tercerparcial/vigenere]

└─$ wget https://artifacts.picoctf.net/c/159/cipher.txt

**Abrimos el archivo**

┌──(kali㉿kali)-[~/picoctf/tercerparcial/vigenere]

└─$ open message.txt
```
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_f85729e7}
```

Accedemos a la pagina: https://www.dcode.fr/cifrado-vigenerepara desencriptar
y la palabra clave es 'CYLAB'

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

**Bandera** picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_d85729g7}

## Notas opcionales.

## Referencias.

https://www.dcode.fr/cifrado-vigenere