# Need For Speed

## Objetivo.

The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? [need-for-speed](https://jupiter.challenges.picoctf.org/static/f9abc386dfb1309e687344783f208b20/need-for-speed).

## Solución.

**Descargar el archivo asm del reto** 

┌──(kali㉿kali)-[~/picoctf/reversing/needforspeed]

└─$ wget https://jupiter.challenges.picoctf.org/static/f9abc386dfb1309e687344783f208b20/need-for-speed

**Checamos que tipo de archivos**

┌──(kali㉿kali)-[~/picoctf/reversing/needforspeed]

└─$ file need-for-speed

```
need-for-speed: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=b4b1e824082c140091043151ab990149efa44806, not stripped
```

Se trata de un archivo de 64 bits.

**Damo permisos y ejecutamos el archivo**

┌──(kali㉿kali)-[~/picoctf/reversing/needforspeed]

└─$ chmod +x need-for-speed

┌──(kali㉿kali)-[~/picoctf/reversing/needforspeed]

└─$ ./need-for-speed

```
Keep this thing over 50 mph!
============================

Creating key...
Not fast enough. BOOM!
```

Nos dice que está generando la llave, pero luego se sale.

**Hacemos un baseado de memoria** 

┌──(kali㉿kali)-[~/picoctf/reversing/needforspeed]

└─$ . objdump -D need-for-speed -M intel | grep '< main >:' -A20

```
000000000000091a <main>:
 91a:   55                      push   rbp
 91b:   48 89 e5                mov    rbp,rsp
 91e:   48 83 ec 10             sub    rsp,0x10
 922:   89 7d fc                mov    DWORD PTR [rbp-0x4],edi
 925:   48 89 75 f0             mov    QWORD PTR [rbp-0x10],rsi
 929:   b8 00 00 00 00          mov    eax,0x0
 92e:   e8 a5 ff ff ff          call   8d8 <header>
 933:   b8 00 00 00 00          mov    eax,0x0
 938:   e8 f2 fe ff ff          call   82f <set_timer>
 93d:   b8 00 00 00 00          mov    eax,0x0
 942:   e8 36 ff ff ff          call   87d <get_key>
 947:   b8 00 00 00 00          mov    eax,0x0
 94c:   e8 5b ff ff ff          call   8ac <print_flag>
 951:   b8 00 00 00 00          mov    eax,0x0
 956:   c9                      leave  
 957:   c3                      ret    
 958:   0f 1f 84 00 00 00 00    nop    DWORD PTR [rax+rax*1+0x0]
 95f:   00 

0000000000000960 <__libc_csu_init>:
```

Se observa que hay un encabezado, timer, generador de llave e imprime la llave.

**Con ayuda de gdb, desensamblamos el código**

```
(gdb) disassemble main
Dump of assembler code for function main:
   0x000000000000091a <+0>:     push   rbp
   0x000000000000091b <+1>:     mov    rbp,rsp
   0x000000000000091e <+4>:     sub    rsp,0x10
   0x0000000000000922 <+8>:     mov    DWORD PTR [rbp-0x4],edi
   0x0000000000000925 <+11>:    mov    QWORD PTR [rbp-0x10],rsi
   0x0000000000000929 <+15>:    mov    eax,0x0
   0x000000000000092e <+20>:    call   0x8d8 <header>
   0x0000000000000933 <+25>:    mov    eax,0x0
   0x0000000000000938 <+30>:    call   0x82f <set_timer>
   0x000000000000093d <+35>:    mov    eax,0x0
   0x0000000000000942 <+40>:    call   0x87d <get_key>
   0x0000000000000947 <+45>:    mov    eax,0x0
   0x000000000000094c <+50>:    call   0x8ac <print_flag>
   0x0000000000000951 <+55>:    mov    eax,0x0
   0x0000000000000956 <+60>:    leave  
   0x0000000000000957 <+61>:    ret    
End of assembler dump.
```

**Creamos un break**

```
(gdb) break main
Breakpoint 1 at 0x91e
(gdb) info breakpoints
Num     Type           Disp Enb Address            What
1       breakpoint     keep y   0x000000000000091e <main+4>
```


**Corremos el programa**

```
(gdb) run
Starting program: /home/frausto_san-picoctf/picoctf/reversing/needforspeed/need-for-speed 
warning: Error disabling address space randomization: Operation not permitted
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x00005588cd40091e in main ()
```

**Desensamblamos otra vez**.

```
(gdb) disassemble main
Dump of assembler code for function main:
   0x00005588cd40091a <+0>:     push   rbp
   0x00005588cd40091b <+1>:     mov    rbp,rsp
=> 0x00005588cd40091e <+4>:     sub    rsp,0x10
   0x00005588cd400922 <+8>:     mov    DWORD PTR [rbp-0x4],edi
   0x00005588cd400925 <+11>:    mov    QWORD PTR [rbp-0x10],rsi
   0x00005588cd400929 <+15>:    mov    eax,0x0
   0x00005588cd40092e <+20>:    call   0x5588cd4008d8 <header>
   0x00005588cd400933 <+25>:    mov    eax,0x0
   0x00005588cd400938 <+30>:    call   0x5588cd40082f <set_timer>
   0x00005588cd40093d <+35>:    mov    eax,0x0
   0x00005588cd400942 <+40>:    call   0x5588cd40087d <get_key>
   0x00005588cd400947 <+45>:    mov    eax,0x0
   0x00005588cd40094c <+50>:    call   0x5588cd4008ac <print_flag>
   0x00005588cd400951 <+55>:    mov    eax,0x0
   0x00005588cd400956 <+60>:    leave  
   0x00005588cd400957 <+61>:    ret    
End of assembler dump.
```

Vemos como el brake esta apuntando.

**Ahora ejecutamos las funciones get_key y print_flag para obtener la bandera**

```
(gdb) call (int) get_key()
Creating key...
Finished
$1 = 9
(gdb) call (int) print_flag()
Printing flag:
PICOCTF{Good job keeping bus #190ca38b speeding along!}
$2 = 56
```

**Bandera** `PICOCTF{Good job keeping bus #190ca38b speeding along!}`

## Notas opcionales.

## Referencias.

Vídeo

https://www.youtube.com/watch?v=2LRa9WLu51c&ab_channel=hackadvisermx