# GDB baby step 2

## Objetivo.

Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Debug [this](https://artifacts.picoctf.net/c/520/debugger0_b).

## Solución.

**Descargar el archivo del reto**

┌──(kali㉿kali)-[~/picoctf/tercerparcial/gdbabystep2]

└─$ wget https://artifacts.picoctf.net/c/512/debugger0_b

**Con ayuda de gdb podemos ver el códifo ensamblador**

┌──(kali㉿kali)-[~/picoctf/tercerparcial/gdbabystep2]

└─$ gdb debugger0_b

```
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:     endbr64 
   0x000000000040110a <+4>:     push   %rbp
   0x000000000040110b <+5>:     mov    %rsp,%rbp
   0x000000000040110e <+8>:     mov    %edi,-0x14(%rbp)
   0x0000000000401111 <+11>:    mov    %rsi,-0x20(%rbp)
   0x0000000000401115 <+15>:    movl   $0x1e0da,-0x4(%rbp)
   0x000000000040111c <+22>:    movl   $0x25f,-0xc(%rbp)
   0x0000000000401123 <+29>:    movl   $0x0,-0x8(%rbp)
   0x000000000040112a <+36>:    jmp    0x401136 <main+48>
   0x000000000040112c <+38>:    mov    -0x8(%rbp),%eax
   0x000000000040112f <+41>:    add    %eax,-0x4(%rbp)
   0x0000000000401132 <+44>:    addl   $0x1,-0x8(%rbp)
   0x0000000000401136 <+48>:    mov    -0x8(%rbp),%eax
   0x0000000000401139 <+51>:    cmp    -0xc(%rbp),%eax
   0x000000000040113c <+54>:    jl     0x40112c <main+38>
   0x000000000040113e <+56>:    mov    -0x4(%rbp),%eax
   0x0000000000401141 <+59>:    pop    %rbp
   0x0000000000401142 <+60>:    ret    
End of assembler dump.
```

Se deben de pasar  607 veces para terminar el codigo, nos ayduaremos de gauss para resolverlo, siendo 
```
s=((1+606)/2)*606, lo que nos da183921
A eso le sumamos el valor de [rbp-0x4] en decimal  es igual a: 123098 Obteniendo el numero de la bandera el cual es 307019
```

**Bandera** picoCTF{307019}

## Notas opcionales.

## Referencias.