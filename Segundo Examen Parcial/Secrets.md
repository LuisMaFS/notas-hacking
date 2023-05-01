# Secrets

## Objetivo.

We have several pages hidden. Can you find the one with the flag?The website is running [here](http://saturn.picoctf.net:65352/).

## Solución.

**Abrimos la página que nos proporciona el reto**

Agregamos secret/ al final de la página: http://saturn.picoctf.net:65352/secret/

Revisamos el código fuente de la página

```
<!DOCTYPE html>
<html>
<head>
<title></title>
<link rel="stylesheet" href="[hidden/file.css](http://saturn.picoctf.net:65352/secret/hidden/file.css)" />
</head>
<body>
<h1>Finally. You almost found me. you are doing well</h1>
<img src="[https://media1.tenor.com/images/0a6aff9f825af62c05adfbd75039cc7b/tenor.gif?itemid=4648337](https://media1.tenor.com/images/0a6aff9f825af62c05adfbd75039cc7b/tenor.gif?itemid=4648337)" alt="Something Like That GIF - Andy Parksandrecreation Wtf GIFs" style="max-width: 833px; background-color: rgb(151, 121, 85);" width="833" height="937.125">
</body>
</html>
```

La pista está en el archivo css.

Entonces agregamos al final de la página hidden: http://saturn.picoctf.net:65352/secret/hidden/

Encontramos otra pista superhidden/ debemos agregarlo al final de la liga http://saturn.picoctf.net:65352/secret/hidden/superhidden/

Ya llegamos a la bandera, hay que encontrarla 

**Bandera** picoCTF{succ3ss_@h3n1c@10n_790d2615}

## Notas opcionales.

## Referencias.

**Vídeo**

https://www.youtube.com/watch?v=40DYCMInk5E&ab_channel=RahulSingh