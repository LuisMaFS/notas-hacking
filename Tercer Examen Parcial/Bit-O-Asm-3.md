# Bit-O-Asm-3

## Objetivo.

Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).

## Solución.

**Descargar el archivo del reto**

┌──(kali㉿kali)-[~/picoctf/tercerparcial/bitoasm3]

└─$ wget https://artifacts.picoctf.net/c/509/disassembler-dump0_c.txt

**Hacemos un cat para ver contenido del archivo**

┌──(kali㉿kali)-[~/picoctf/tercerparcial/bitoasm3]

└─$ cat disassembler-dump0_c.txt

```
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a
<+22>:    mov    DWORD PTR [rbp-0x8],0x4
<+29>:    mov    eax,DWORD PTR [rbp-0xc]
<+32>:    imul   eax,DWORD PTR [rbp-0x8]
<+36>:    add    eax,0x1f5
<+41>:    mov    DWORD PTR [rbp-0x4],eax
<+44>:    mov    eax,DWORD PTR [rbp-0x4]
<+47>:    pop    rbp
<+48>:    ret
```

El valor 0x9fe1a va a eax. Luego se multiplica por 0x4. El resultado de la multiplicación es: 0x27f868, a esto se le anade 0x1f5.

Dando como resultado: 0x27fa5d. Luego se va a rbp-0x4 y de regreso a eax 0x27fa5d al final da 2619997

**Bandera** picoCTF{2619997}

## Notas opcionales.

## Referencias.