# Mind your Ps and Qs

## Objetivo.

In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/12d820e355a7775a2c9129b2622a7eb6/values)

## Solución.

**Descargar los valores para el reto
┌──(kali㉿kali)-[~/picoctf/crypto/mindpsqs]

└─$ wget https://mercury.picoctf.net/static/12d820e355a7775a2c9129b2622a7eb6/values    

**Hacer cat a los valores**
┌──(kali㉿kali)-[~/picoctf/crypto/mindpsqs]

└─$ cat values
```
Decrypt my super sick RSA:
c: 843044897663847841476319711639772861390329326681532977209935413827620909782846667
n: 1422450808944701344261903748621562998784243662042303391362692043823716783771691667
e: 65537 
```

*Se observa que son valores RSA*

**Usando python podemos obtener la bandera**

┌──(kali㉿kali)-[~]

└─$ python3
```
Python 3.11.2 (main, Mar 13 2023, 12:18:29) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse
>>> 
>>> c = 843044897663847841476319711639772861390329326681532977209935413827620909782846667
>>> e = 65537
>>> p = 2159947535959146091116171018558446546179
>>> q = 658558036833541874645521278345168572231473
>>> 
>>> n = p * q
>>> n
1422450808944701344261903748621562998784243662042303391362692043823716783771691667
>>> 
>>> tn = (p-1)*(q-1)
>>> tn
1422450808944701344261903748621562998783582944057933890341955406374353056752914016
>>> 
>>> d = inverse(e,tn)
>>> d
975120122884150896343356420256053234758228648361853546720066993334766006694511009
>>> 
>>> m = pow(c,d,n)
>>> m
13016382529449106065927291425342535437996222135352905256639555294957886055592061
>>> 
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_00264570}'
```

**Para obtener q y p se factorizó en dos numeros a n, usando una herramienta web**

**Bandera** 
picoCTF{sma11_N_n0_g0od_00264570}

## Notas opcionales.


## Referencias.

http://www.factordb.com/

Vídeo

https://www.youtube.com/watch?v=pwGSp_4YHTg&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=44&ab_channel=hackadvisermx