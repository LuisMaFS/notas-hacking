# Insp3ctor

## Objetivo.

Kishor Balan tipped us off that the following code may need inspection: `https://jupiter.challenges.picoctf.org/problem/9670/` ([link](https://jupiter.challenges.picoctf.org/problem/9670/)) or http://jupiter.challenges.picoctf.org:9670

## Solución.

1. Abrir el link que direcciona a la página, click derecho, ver código fuente de la página y obtenemos la primer parte de la bandera:
picoCTF{tru3_d3
2. Click derecho, inspeccionar, dirigirse a la pestaña source, dentro de source, buscar el archivo mycss.css. Aquí se encontrará la segunda parte de la bandera
t3ct1ve_0r_ju5t
3. Ahí mismo, (la sección source) nos dirigimos al archivo myjs.js. Aquí encontramos la tercera parte de la bandera
Es esta_lucky?2e7b23e3}

Juntamos las partes y quedá así:
picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?2e7b23e3}

## Notas opcionales.

Este reto sirvió de repaso a HTML, CSS y JS

## Referencias.

https://www.youtube.com/watch?v=L_t9csko7tI&t=42s&ab_channel=MikeOnTech