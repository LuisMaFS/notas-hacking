# Search source

## Objetivo.

The developer of this website mistakenly left an important artifact in the website source, can you find it?The website is [here](http://saturn.picoctf.net:50303/)

## Solución.

**Abrimos la página que nos proporciona el reto**

Revisamos su código fuente en busca de la bandera.

En el estilo de css.

```
/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_587d12b8} **/
 .carousel-indicators li {
     width: 20px;
     height: 20px;
     border-radius: 11px;
     background-color: #070000;
```

**Bandera** picoCTF{1nsp3ti0n_0f_w3bpag3s_587d12b8}

## Notas opcionales.

## Referencias.

**Vídeo**

https://www.youtube.com/watch?v=8raoDvjEZ6Y&ab_channel=AlmondForce