# WebNet0

## Objetivo.

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

## Solución.

**Descargar la captura de paquetes y la llave que proporciona el reto**

**Los streams TLS, están encriptados, usando la llave podemos acceder a su contenido**

**En wireshark debemos editar las preferencias y escojer como protocolo TLS, después incluir la llave**

**Seguido podemos hacer una busqueda de una cadena, que contenga la bandera, sabemos que inicia con picoCTF**

**Bandera**
 
picoCTF{nongshim.shrimp.crackers}

## Notas opcionales.

**TLS**

Transport Layer Security (TLS) es un protocolo criptográfico diseñado para proporcionar seguridad en las comunicaciones a través de una red informática. El protocolo se usa ampliamente en aplicaciones como correo electrónico, mensajería instantánea y voz sobre IP, pero su uso para proteger HTTPS sigue siendo el más visible públicamente.

El protocolo TLS tiene como objetivo principal proporcionar seguridad, incluida la privacidad (confidencialidad), la integridad y la autenticidad mediante el uso de criptografía, como el uso de certificados, entre dos o más aplicaciones informáticas que se comunican. Se ejecuta en la capa de presentación y se compone de dos capas: el registro TLS y los protocolos de protocolo de enlace TLS.

## Referencias.

**Vídeo**

https://www.youtube.com/watch?v=9uflLPoETOc&ab_channel=hackadvisermx

**Recursos**

https://en.wikipedia.org/wiki/Transport_Layer_Security
