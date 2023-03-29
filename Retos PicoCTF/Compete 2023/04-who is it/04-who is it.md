# who is it

## Objetivo

Someone just sent you an email claiming to be Google's co-founder Larry Page but you suspect a scam.Can you help us identify whose mail server the email actually originated from?Download the email file [here](https://artifacts.picoctf.net/c/499/email-export.eml). Flag: picoCTF{FirstnameLastname}

## Hints

*  whois can be helpful on IP addresses also, not only domain names.

## Solución

### Solución 1
```
Hay que identificar la IP del correo:
173.249.33.206
Y una vez que se identifique, hay que meterlo en DomainTools para ver todos los datos y investigar el nombre de la persona de donde se originó realmente el correo electrónico
```
![[Datos.png]]

## Flag

picoCTF{WilhelmZwalina}

## Notas adicionales

Una dirección IP es una dirección única que identifica a un dispositivo en Internet o en una red local. IP significa “protocolo de Internet”, que es el conjunto de reglas que rigen el formato de los datos enviados a través de Internet o la red local.

## Referencias

[DomainTools](https://whois.domaintools.com/173.249.33.206)
[IP](https://latam.kaspersky.com/resource-center/definitions/what-is-an-ip-address)
