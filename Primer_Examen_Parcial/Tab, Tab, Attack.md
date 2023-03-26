# Tab, Tab, Attack

## Objetivo.

Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/e38f6a5b69b45d21e33cf7281d8c2531/Addadshashanammu.zip)

## Solución.

**Descargamos el archivo zip https://mercury.picoctf.net/static/e38f6a5b69b45d21e33cf7281d8c2531/Addadshashanammu.zip en el shell de picoCTF**

**Desempacquetamos el archivo, podemos ver que s ehan generado muchas carpetas**
frausto_san-picoctf@webshell:~$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
frausto_san-picoctf@webshell:~$  
frausto_san-picoctf@webshell:~$ 

**Accedemos a cada una de las carpetas**
frausto_san-picoctf@webshell:~$ cd Addadshashanammu/
frausto_san-picoctf@webshell:~/Addadshashanammu$ cd Almurbalarammi/
frausto_san-picoctf@webshell:~/Addadshashanammu/Almurbalarammi$ cd Ashalmimilkala/
frausto_san-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala$ cd Assurnabitashpi/
frausto_san-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi$ ls
Maelkashishi
frausto_san-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi$ cd Maelkashishi/ 
frausto_san-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi$ cd Onnissiralis/
frausto_san-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis$ cd Ularradallaku/
frausto_san-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet

**Usamos el comando stat para ver el estado del archivo fang-og-haynekhtnamet**
frausto_san-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ stat fang-of-haynekhtnamet 
  File: fang-of-haynekhtnamet
  Size: 8320            Blocks: 24         IO Block: 4096   regular file
Device: 10301h/66305d   Inode: 37881773    Links: 1
Access: (0755/-rwxr-xr-x)  Uid: (10000/frausto_san-picoctf)   Gid: (10000/frausto_san-picoctf)
Access: 2021-03-16 01:16:35.000000000 +0000
Modify: 2021-03-16 01:16:35.000000000 +0000
Change: 2023-03-20 23:29:30.393183040 +0000
 Birth: 2023-03-20 23:29:30.389183036 +0000

**Con ./fang-of-haynekhtnamet obtenemos la bandera**
frausto_san-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ./fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_f3553887}
frausto_san-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$

## Notas opcionales.

**STAT:** El comando Stat es utilizado en el sistema Linux o Unix con el objetivo de **mostrar información a detalle sobre archivos y sistemas de archivos**.

## Referencias.

https://www.youtube.com/watch?v=D9Lll1NXAiA&ab_channel=pwnified
https://keepcoding.io/blog/que-es-el-comando-stat-y-como-usarlo-en-linux/#:~:text=El%20comando%20Stat%20es%20utilizado,su%20tama%C3%B1o%2C%20permisos%20e%20inodos.