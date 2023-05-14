# asm3

## Objetivo.

What does asm3(0xba6c5a02,0xd101e3dd,0xbb86a173) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/cb753ae52bca4aa303deca5fbfb01bfb/test.S)

## Solución.

**Descargar el archivo asm del reto** 

┌──(kali㉿kali)-[~/picoctf/reversing/asm3]

└─$ wget https://jupiter.challenges.picoctf.org/static/cb753ae52bca4aa303deca5fbfb01bfb/test.S

**El programa asm contiene lo siguiente:**

```
asm3:
	<+0>:	push   ebp
	<+1>:	mov    ebp,esp
	<+3>:	xor    eax,eax
	<+5>:	mov    ah,BYTE PTR [ebp+0xb]
	<+8>:	shl    ax,0x10
	<+12>:	sub    al,BYTE PTR [ebp+0xd]
	<+15>:	add    ah,BYTE PTR [ebp+0xc]
	<+18>:	xor    ax,WORD PTR [ebp+0x12]
	<+22>:	nop
	<+23>:	pop    ebp
	<+24>:	ret 
	
```

**En un simulador hacemos lo siguiente**

```
start:
	push 0xbb86a173
	push 0xd101e3dd
	push 0xba6c5a02
	call asm3
	
asm3:
	push   ebp
	mov    ebp,esp
	xor    eax,eax
	mov    ah,BYTE PTR [ebp+0xb]
	shl    ax,0x10
	sub    al,BYTE PTR [ebp+0xd]
	add    ah,BYTE PTR [ebp+0xc]
	xor    ax,WORD PTR [ebp+0x12]
	nop
	pop    ebp
	ret 
```

**El resultado del programa es el siguiente*

```
EAX  0x0000669B
EBX  0x00000000
ECX  0x00000000
EDX  0x00000000
ESI  0x00000000
EDI  0x00000000
EBP  0x000203F0
ESP  0x000203F0
EIP  0x0002042C

Ln 15, Col 2
Flags
Carry  0
Dir  0
Int  0
Overflow  0
Sign  0
Zero  0

```

El valor de eax es la bandera

**Bandera** 0x669B

## Notas opcionales.

## Referencias.

Vídeo

https://www.youtube.com/watch?v=Dy-gHlymkdo&ab_channel=hackadvisermx