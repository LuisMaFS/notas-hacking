## Descripción
You will find the flag after decrypting this file Download the encrypted flag [here](https://artifacts.picoctf.net/c/447/encrypted.txt).!

## Hints
+ Sometimes rotation is right


## Solución
``` bash
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $cat encrypted.txt 
xqkwKBN{z0bib1wv_l3kzgxb3l_73l97nm4}
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼
```


## Flag

``` picoCTF{r0tat1on_d3crypt3d_73d97fe4} ```


## Notas adicionales

Utilizando cyberchef se va rotando la cadena de texto hasta encontrar una cadena mas legible, en este caso fueron 18 rotaciones. 


## Referencias
+ [Cyberchef](https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,18)&input=eHFrd0tCTnt6MGJpYjF3dl9sM2t6Z3hiM2xfNzNsOTdubTR9)
