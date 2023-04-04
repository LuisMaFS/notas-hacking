# MacroHard WeakEdge

## Objetivo.

I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/3944a59474f9f676942282c50b9c3675/Forensics%20is%20fun.pptm)

## Solución.

**Revisar el tipo de archivo**

┌──(kali㉿kali)-[~/picoctf/forensic/macrohard]

└─$ file Forensics\ is\ fun.pptm 

Forensics is fun.pptm: Microsoft PowerPoint 2007+

**Es un archivo PowerPoint 2007 con macros habilitadas**

**Desempaquetar el archivo**

┌──(kali㉿kali)-[~/picoctf/forensic/macrohard]

└─$ unzip Forensics\ is\ fun.pptm 

**Con la ayuda de visual code, podemos revisar entre carpetas**
**En la carpeta ppt, hay un archivo llamado hidden, dentro contiene, una secuencia extraña en base 64**

Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q

**Si la convertimos a texto podremos ver de que se trata**

┌──(kali㉿kali)-[~/picoctf/forensic/macrohard]

└─$ echo "Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q" | tr -d " " | base64 -d

flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: invalid input


## Notas opcionales.

## Referencias.

**Vídeo**

https://www.youtube.com/watch?v=CsCeOp9PFGs&ab_channel=hackadvisermx