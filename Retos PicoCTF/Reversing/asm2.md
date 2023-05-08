# asm2

## Objetivo.

What does asm2(0xb,0x2e) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S)

## Solución.

**Descargar el archivo asm del reto** 

┌──(kali㉿kali)-[~/picoctf/reversing/asm2]

└─$ wget https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S

**El programa asm contiene lo siguiente:**

```
asm2:
	<+0>:	push   ebp
	<+1>:	mov    ebp,esp
	<+3>:	sub    esp,0x10
	<+6>:	mov    eax,DWORD PTR [ebp+0xc]
	<+9>:	mov    DWORD PTR [ebp-0x4],eax
	<+12>:	mov    eax,DWORD PTR [ebp+0x8]
	<+15>:	mov    DWORD PTR [ebp-0x8],eax
	<+18>:	jmp    0x509 <asm2+28>
	<+20>:	add    DWORD PTR [ebp-0x4],0x1
	<+24>:	sub    DWORD PTR [ebp-0x8],0xffffff80
	<+28>:	cmp    DWORD PTR [ebp-0x8],0x63f3
	<+35>:	jle    0x501 <asm2+20>
	<+37>:	mov    eax,DWORD PTR [ebp-0x4]
	<+40>:	leave  
	<+41>:	ret  
	
```

**Tenemos un parametro que es**

0xb,0x2e

**El programa consiste en una pila**
```
[   ] <- esp
[   ] <- ebp - 0xc
[-0xffffff75] <- ebp - 0x8
[0x2f] <- ebp - 0x4
[ebp] <- ebp
[ret] <- ebp + 0x4
[0xb] <- ebp + 0x8
[0x2e]<- ebp + 0xc
fffff

registers
[ 0x2e ] eax
[ 0xb ] eax
```

**En python haremos las ejecuciones de instrucciones del programa**

```
frausto_san-picoctf@webshell:~$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
>>> 0xb <= 0x63f3
True
```

Comparar lo que hay en epb - 0x8 con 0x63f3, para saber si es menor o igual, lo cual es correcto.

Y pasamos a las siguientes ejecuciones, que es sumarle 1 a lo que hay en epb - 0x4

```
>>> hex(0x2e + 0x1)
'0x2f'
```

Después sigue una resta, de lo que hay en epb - 0x8 menos 0xffffff80 

```
>>> hex(0xb-0xffffff80)
'-0xffffff75'
```

Volvemos a repetir la comparación del contenido de ebp -0x8 con 0x63f3, y la condición se vuelve a cumplir. Por lo que repetiremos los pasos anteriores una vez más

Para saber cuantos ciclos tendremos que hacer para llegar a:0x63f3 realizamos lo siguiente

```
>>> 0x63f3 / 0xffffff80
5.957437856717046e-06
```

Al rededor de unas 6 vueltas aprox.

El valor original de ebp - 0x8 era de 0x2e
Entonces calculamos:

```
>>> int(0x2e)
46
>>> hex(46 + 6)
'0x34'
```

**Bandera** 0x34

## Notas opcionales.

## Referencias.

Vídeo

https://www.youtube.com/watch?v=Dy-gHlymkdo&ab_channel=hackadvisermx