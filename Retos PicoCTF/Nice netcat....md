# Nice netcat...

## Objetivo.

There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 22342`, but it doesn't speak English...

## Solución.

**Abrir el webshell de picoctf y ejecutar el comando netcat nc mercury.picoctf.net 22342, nos regresará varios números decimales**
frausto_san-picoctf@webshell:~$ nc mercury.picoctf.net 22342
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
53 
102 
98 
53 
101 
53 
49 
100 
125 
10 

**En la página rapidtables podemos convertir de decimal a texto ASCII, la codificación de todos los números nos da la bandera**
picoCTF{g00d_k1tty!_n1c3_k1tty!_5fb5e51d}

## Notas opcionales.

En este reto retomamos el uso de netcat y la conversión entre bases y código ASCII, al parecer en la seguridad de redes de computadoras, estos temas son mut recurrentes.

## Referencias.

https://www.rapidtables.com/convert/number/ascii-hex-bin-dec-converter.html