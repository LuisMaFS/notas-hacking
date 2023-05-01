# Roboto Sans

## Objetivo.

The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:61304/) out.

## Solución.

**Abrimos la página que nos proporciona el reto**

Agregamos robots.txt al final de la página: http://saturn.picoctf.net:61304/robots.txt

```
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/
```

Después esta parte anMvbXlmaWxlLnR4dA== la desencriptamos en cyberchef base 64.

Nos regresa: js/myfile.txt

Entonces agregamos al final de la página: http://saturn.picoctf.net:61304/js/myfile.txt y obtenemos la bandera.

**Bandera** picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}

## Notas opcionales.

## Referencias.

**Vídeo**

https://www.youtube.com/watch?v=4J-Nse2bKtc&ab_channel=RahulSingh