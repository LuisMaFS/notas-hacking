
## Descripción
Can you make sense of this file? Download the file [here](https://artifacts.picoctf.net/c/293/enc_flag).

## Hints
+ Multiple decoding is always good.


## Solución
``` bash
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $ls
01-Rotation.md    03-hideme.md       enc_flag       flag.png             readmycert.csr
02-ReadMyCert.md  04-Repetitions.md  encrypted.txt  _flag.png.extracted
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $cat enc_flag 
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFZhTTBKVVZGWmFWbVF4V1hoYVNHUlNDbUpXUmpOVVZscFhWbTFHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $base64 -d enc_flag > temp1.txt 
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $cat temp1.txt 
VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVX
bUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdW
MlZzVWxaVmJFNW9UVVJDTlZaWE1XRlVaM0JUVFZaVmQxWXhaSGRSCmJWRjNUVlpXVm1GdGVFVlhi
bTkzVDFWT2JsQlVNRXNLCg==
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $base64 -d temp1.txt > temp2.txt 
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $cat temp2.txt
V1RCa2MyRnRTWGRVYkZaVFltNVNjRmRXYUU5aVJUVnhWVzFhYVdGck5UWmFSVkpQWVRGbmVWVnVR
bHBsYTBweVUxWmpNRTVHWjNsVgpXR1JyVFdwV2VsUlZVbE5oTURCNVZXMWFUZ3BTTVZVd1YxZHdR
bVF3TVZWVmFteEVXbm93T1VOblBUMEsK
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $base64 -d temp2.txt > temp3.txt 
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $base64 -d temp3.txt > temp4.txt 
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $cat temp4.txt
Y0dsamIwTlVSbnRpWVhObE5qUmZiak56ZEROa1gyUnBZekJrSVc0NFgyUXdkMjVzTURSa00yUmZN
R1U0WWpBd01UUjlDZz09Cg==
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $base64 -d temp4.txt > temp5.txt 
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $cat temp5.txt
cGljb0NURntiYXNlNjRfbjNzdDNkX2RpYzBkIW44X2Qwd25sMDRkM2RfMGU4YjAwMTR9Cg==
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $base64 -d temp5.txt > temp6.txt 
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $cat temp6.txt 
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_0e8b0014}
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $

```


## Flag

``` picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_0e8b0014} ```


## Notas adicionales
Al ver el contenido del archivo nos damos cuenta de que se encuentra codificado en base64, con ayuda de la terminal se crean archivos temporales para permitir grabar la decodificacion en cada paso.



## Referencias
+ [base64](https://linuxhint.com/bash_base64_encode_decode/)
