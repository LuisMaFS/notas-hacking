# Pixelated

## Objetivo.

I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled2.png)

## Solución.

**Descargar las imagenes para el reto**

┌──(kali㉿kali)-[~/picoctf/crypto/pixelated]

└─$ wget https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled2.png

┌──(kali㉿kali)-[~/picoctf/crypto/pixelated]

└─$ wget https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled1.png

**Con un script de python podremos juntar las imagenes en una sola y poder ver la bandera**
```
from PIL import Image
import numpy as np

imagen1 = np.asarray( Image.open('scrambled1.png') )
imagen2 = np.asarray( Image.open('scrambled2.png') )

print(imagen1)
print(imagen2)

datos = imagen1.copy() + imagen2.copy()

nueva = Image.fromarray(datos)

nueva.save('nueva.png','PNG')
```

**Si ejecutamo el programa, observamos que son operaciones con matrices por las imagenes y aparte se genera una nueva imagen**

┌──(kali㉿kali)-[~/picoctf/crypto/pixelated]

└─$ python3 exp.py
```
[[[ 82 219   0]
  [227 108   7]
  [183 250  58]
  ...
  [ 30  78 120]
  [ 27   2 119]
  [ 78 127 126]]

 [[185  90 144]
  [ 15 244  26]
  [ 94 245  68]
  ...
  [109 243  21]
  [  8 165 114]
  [143 211  87]]

 [[141 231 170]
  [209 208 168]
  [226 146 162]
  ...
  [  7 177 176]
  [188 118 102]
  [ 56  22 141]]

 ...

 [[ 27 158 100]
  [ 40 159 139]
  [213 114 112]
  ...
  [ 97 196  65]
  [ 15 111 133]
  [207 154  35]]

 [[139  11 181]
  [ 60 222 152]
  [ 53  25 165]
  ...
  [220 138  59]
  [ 55  95 162]
  [114 126 120]]

 [[187  51 204]
  [147  16 107]
  [162 124 181]
  ...
  [104 119  63]
  [110 239 106]
  [247 210  93]]]
[[[173  36 255]
  [ 28 147 248]
  [ 72   5 197]
  ...
  [225 177 135]
  [228 253 136]
  [177 128 129]]

 [[ 70 165 111]
  [240  11 229]
  [161  10 187]
  ...
  [146  12 234]
  [247  90 141]
  [112  44 168]]

 [[114  24  85]
  [ 46  47  87]
  [ 29 109  93]
  ...
  [248  78  79]
  [ 67 137 153]
  [199 233 114]]

 ...

 [[228  97 155]
  [215  96 116]
  [ 42 141 143]
  ...
  [158  59 190]
  [240 144 122]
  [ 48 101 220]]

 [[116 244  74]
  [195  33 103]
  [202 230  90]
  ...
  [ 35 117 196]
  [200 160  93]
  [141 129 135]]

 [[ 68 204  51]
  [108 239 148]
  [ 93 131  74]
  ...
  [151 136 192]
  [145  16 149]
  [  8  45 162]]]
```  

**Abrimos la imagen y vemos la bandera**

┌──(kali㉿kali)-[~/picoctf/crypto/pixelated]

└─$ ls

exp.py  nueva.png  scrambled1.png  scrambled2.png

┌──(kali㉿kali)-[~/picoctf/crypto/pixelated]

└─$ open nueva.png 

**Bandera**
picoCTF{7188864c}

## Notas opcionales.

**Teoría**

**Crptografía visual**

La criptografía visual es una técnica criptográfica que permite cifrar información visual (imágenes, texto, etc.) de tal forma que la información descifrada aparece como una imagen visual. Una de las técnicas más conocidas se atribuye a Moni Naor y Adi Shamir, quienes la desarrollaron en 1994.

## Referencias.

**Vídeo**

https://www.youtube.com/watch?v=zWU6MV8dQQ4&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=43&ab_channel=hackadvisermx