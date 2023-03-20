# Scavenger Hunt

## Objetivo.

There is some interesting information hidden around this site [http://mercury.picoctf.net:27393/](http://mercury.picoctf.net:27393/). Can you find it?

## Solución.

Se parece a un reto web ya realizado (robots). Lo primero que debemos hacer es ver el código fuente de la página, aquí obtenemos la primer parte de la bandera:
**picoCTF{t**

Ahora inspeccionaremos la página, en la hoja de estilos, (css) se encuentra la segunda parte de la bandera:
**h4ts_4_l0**

Checamos la parte de JavaScript, no hay fragmento de bandera pero hay una pista.
**¿Cómo puedo dejar fuera a Google del index de mi página?**
Entonces ingresamos a: http://mercury.picoctf.net:27393/robots.txt
Y obtenemos la tercera parte de la bandera:
**t_0f_pl4c**

Nos vuelven a dar una pista
**Yo pienso que es un servidor Apache, ¿Puedes entrar a la bandera?**
Entonces ingresamos a: http://mercury.picoctf.net:27393/.htaccess
Y obtenemos la cuarta parte de la bandera:
**3s_2_lO0k**

Y nos da otra pista
**I love making websites on my Mac, I can Store a lot of information there.**
Entonces ingresamos a: http://mercury.picoctf.net:27393/.DS_Store
Y obtenemos la quinta parte de la bandera que es_d375c750}

Juntamos todas las partes y queda así:
**picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_d375c750}**

## Notas opcionales.

**.htacccess**
Es un archivo de configuración del **software de servidor Apache**, que contiene las directivas que definen el comportamiento de Apache. El archivo.htaccess indica en todo momento qué puede hacer y qué no el usuario que visita un sitio web.

**DS_Store**
En el sistema operativo macOS de Apple, **.DS Store** es un archivo que almacena atributos personalizados de la carpeta que lo contiene, como la posición de los iconos o la imagen de fondo.

## Referencias.

https://www.youtube.com/watch?v=E2gN3AGHirc