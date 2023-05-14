# GDB Test Drive

## Objetivo.

#### Description

Can you get the flag?Download this [binary](https://artifacts.picoctf.net/c/86/gdbme).
Here's the test drive instructions:

-   `$ chmod +x gdbme`
-   `$ gdb gdbme`
-   `(gdb) layout asm`
-   `(gdb) break *(main+99)`
-   `(gdb) run`
-   `(gdb) jump *(main+104)`

## Solución.

**Descargar el archivo asm del reto** 

┌──(kali㉿kali)-[~/picoctf/reversing/gdbtestdrive]

└─$ wget https://artifacts.picoctf.net/c/86/gdbme

**Checamos que tipo de archivo es**

┌──(kali㉿kali)-[~/picoctf/reversing/gdbtestdrive]

└─$ file gdbme

```
gdbme: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=f06e32e5be0bde84aacbdef5488db9f2ad7db4a0, for GNU/Linux 3.2.0, not stripped
```

Se trata de un archivo de 64 bits.

**Damo permisosde ejecución al archivo y aplicamos gdb**

┌──(kali㉿kali)-[~/picoctf/reversing/gdbtestdrive]

└─$ chmod +x gdbme

**Dentro de gdb aplicamos lo siguiente (gdb) layout asm**

Mostraría el contenido del archivo ensamblador

![[Captura de pantalla (1378).png]]

**Ahora aplicamos: break * (main+99)**

```
(gdb)break *(main+99)
Breakpoint 1 at 0x312a
```

Crea un apuntador a un break.

**Corremos** 

```
(gdb) run
Undefined command "". Try "help".
```

Nos manda que no puede reconecer a "" 

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
Starting program: /home/frausto_san-picoctf/picoctf/reversing/drivetest/gdbme 
warning: Error disabling address space randomization: Operation not permitted
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000055717c59732a in main ()
```

**Después ejecutamos el salto**.

```
(gdb) jump *(main+104)
Continuing at 0x55717c59732f.
picoCTF{d3bugg3r_dr1v3_72bd8355}
[Inferior 1 (process 271) exited normally]
```

**Bandera** picoCTF{d3bugg3r_dr1v3_72bd8355}

## Notas opcionales.

## Referencias.
