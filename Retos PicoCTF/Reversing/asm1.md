# asm1

## Objetivo.

What does asm1(0x8be) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/66c927e32f3d7be7a62d13a7c2250943/test.S)

## Solución.

**Descargar el archivo asm del reto** 

┌──(kali㉿kali)-[~/picoctf/reversing/asm1]

└─$ wget https://jupiter.challenges.picoctf.org/static/66c927e32f3d7be7a62d13a7c2250943/test.S

**El programa asm contiene lo siguiente:**

```
asm1:
	<+0>:	push   ebp
	<+1>:	mov    ebp,esp
	<+3>:	cmp    DWORD PTR [ebp+0x8],0x71c
	<+10>:	jg     0x512 <asm1+37>
	<+12>:	cmp    DWORD PTR [ebp+0x8],0x6cf
	<+19>:	jne    0x50a <asm1+29>
	<+21>:	mov    eax,DWORD PTR [ebp+0x8]
	<+24>:	add    eax,0x3
	<+27>:	jmp    0x529 <asm1+60>
	<+29>:	mov    eax,DWORD PTR [ebp+0x8]
	<+32>:	sub    eax,0x3
	<+35>:	jmp    0x529 <asm1+60>
	<+37>:	cmp    DWORD PTR [ebp+0x8],0x8be
	<+44>:	jne    0x523 <asm1+54>
	<+46>:	mov    eax,DWORD PTR [ebp+0x8]
	<+49>:	sub    eax,0x3
	<+52>:	jmp    0x529 <asm1+60>
	<+54>:	mov    eax,DWORD PTR [ebp+0x8]
	<+57>:	add    eax,0x3
	<+60>:	pop    ebp
	<+61>:	ret 
	
```

**Tenemos un parametro que es**

0x8be

**El programa consiste en una pila**
```
stack

0000
[ebp] <- esp <- ebp
[ret] <- ebp + 0x4
[0x8be] <- ebp + 0x8
fffff

registers
[ 0x8be ] eax
[ 0x8bb ] eax
```

**En python haremos las ejecuciones de instrucciones del programa**

```
frausto_san-picoctf@webshell:~$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
>>> 0x8be > 0x71c
True
```

La primer ejecución es correcta, 0x8be es mayor que 0x71c, saltamos a la línea 37

```
>>> 0x8be !=  0x8be
False
```
La segunda comparación, es para saber si son diferentes las cifras, lo cual es falso.

La siguiente instrucción e guardar DWORD en EAX

Después sigue una resta, de la palabra menos 3 y el resultado lo guardamos en hexadecimal

```
>>> hex(0x8be-0x3)
'0x8bb'
```
Saltamos a la línea 60, lo que nos indica sacar el contenido del registro eax y regresar al main

**Bandera** 0x8bb

## Notas opcionales.

## Referencias.

Vídeo

https://www.youtube.com/watch?v=Dy-gHlymkdo&ab_channel=hackadvisermx