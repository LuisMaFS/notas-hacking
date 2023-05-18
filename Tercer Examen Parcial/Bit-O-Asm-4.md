# Bit-O-Asm-4

## Objetivo.

Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).
## Solución.

**Descargar el archivo del reto**

┌──(kali㉿kali)-[~/picoctf/tercerparcial/bitoasm3]

└─$ wget https://artifacts.picoctf.net/c/509/disassembler-dump0_d.txt

**Hacemos un cat para ver contenido del archivo**

┌──(kali㉿kali)-[~/picoctf/tercerparcial/bitoasm3]

└─$ cat disassembler-dump0_d.txt

```
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    cmp    DWORD PTR [rbp-0x4],0x2710
<+29>:    jle    0x55555555514e <main+37>
<+31>:    sub    DWORD PTR [rbp-0x4],0x65
<+35>:    jmp    0x555555555152 <main+41>
<+37>:    add    DWORD PTR [rbp-0x4],0x65
<+41>:    mov    eax,DWORD PTR [rbp-0x4]
<+44>:    pop    rbp
<+45>:    ret
```

El valor es mayor por lo que no salta a la dirección 37 Se resta 0x65 de 0x9fe1a en deciamal es:  654773

**Bandera** picoCTF{654773}

## Notas opcionales.

## Referencias.