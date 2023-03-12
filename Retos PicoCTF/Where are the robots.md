# Where are the robots

## Objetivo.

Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/56830/`

## Solución.

En la barra de busqueda aparece el link: `https://jupiter.challenges.picoctf.org/problem/56830/`
al final de este escribimos robots.txt.
redirigirá a una página que muestra la siguiente información

User-agent: *
Disallow: /1bb4c.html

Hay que pegar esto /1bb4c.html al final del link, se redireccionará a una página que muestra la bandera.

picoCTF{ca1cu1at1ng_Mach1n3s_1bb4c}

## Notas opcionales.

Un archivo robots.txt indica a los rastreadores de los buscadores a qué URLs de tu sitio pueden acceder. Principalmente, se utiliza para evitar que las solicitudes que recibe tu sitio lo sobrecarguen

## Referencias.

https://www.youtube.com/watch?v=pdMMq64D0OU&ab_channel=MikeOnTech
https://developers.google.com/search/docs/crawling-indexing/robots/intro?hl=es