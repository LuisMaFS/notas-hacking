## Descripción
How about we take you on an adventure on exploring certificate signing requests Take a look at this CSR file [here](https://artifacts.picoctf.net/c/379/readmycert.csr).

## Hints
+ Download the certificate signing request and try to read it.


## Solución
``` bash
┌──[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $
┌──[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $ls
encrypted.txt  readmycert.csr  Rotation.md
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $cat readmycert.csr 
-----BEGIN CERTIFICATE REQUEST-----
MIICpzCCAY8CAQAwPDEmMCQGA1UEAwwdcGljb0NURntyZWFkX215Y2VydF8xMmVi
YTdmMX0xEjAQBgNVBCkMCWN0ZlBsYXllcjCCASIwDQYJKoZIhvcNAQEBBQADggEP
ADCCAQoCggEBALpy6fpMuQHtDwrurMECVwArITyhZEWWOtGLTteR7QMx67dfVxm3
jEHlsrbVQtJBdMJDuMA3eRp14c3tD3GTf/BkLbvjuvfha/3yqmuRHg9QUoYb9129
+TQdefx9zF2Rfi3LRh/EBr63nOW30u/2grNCYloHJsECfl/yx6UxKgu64uEUbaMC
ds9CRgDj1dRT6OY9OR3VozOHBacX9VpdoCDxJZHEsEwF9qd09NinMqsqDl9DHTyq
rlwsAK5qpsoiKvHs0+Li5oHe8iVqtb9E55lMRZDG88yw9y6cbwDWFh0sgt2k6kz7
WcrUV9cignn6lsJ6sAbguYiPOXxQUdsP8fkCAwEAAaAmMCQGCSqGSIb3DQEJDjEX
MBUwEwYDVR0lBAwwCgYIKwYBBQUHAwIwDQYJKoZIhvcNAQELBQADggEBAESOpr8K
qI7FafXaK9fJslzdYXQpl/ByCM1J+ZYiSLzBh3XQKX6DED2glrAkizQmNRn7Td3v
TRRFGuxFF2rhyEyLiZG1YXFs0xlBTLKDFKYegwqj1L7UDOtA9mNJuJkuuFnfK/EI
eB0mEOldJJSdHobOvB7GApwKiVqmTiOEVUu2gD+ec9xAFg9duzdfluPQ+DAmZvnt
Jip/lE65xoqG6tIvf2Z9U9fo6zC3pBx+vtBHGYtXEjuTfzhc9M7S7puaC+Gz84gM
eZ96LXuAlFDXYYbSGuQxsIkYAobpbb8SkUxy+g7Z8YKLb85KT9UnHyKfvHbzw9Sn
uByIlA+gSIKNIJ0=
-----END CERTIFICATE REQUEST-----
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $openssl req -text -in readmycert.csr 
Certificate Request:
    Data:
        Version: 1 (0x0)
        Subject: CN = picoCTF{read_mycert_12eba7f1}, name = ctfPlayer
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption
                RSA Public-Key: (2048 bit)
                Modulus:
                    00:ba:72:e9:fa:4c:b9:01:ed:0f:0a:ee:ac:c1:02:
                    57:00:2b:21:3c:a1:64:45:96:3a:d1:8b:4e:d7:91:
                    ed:03:31:eb:b7:5f:57:19:b7:8c:41:e5:b2:b6:d5:
                    42:d2:41:74:c2:43:b8:c0:37:79:1a:75:e1:cd:ed:
                    0f:71:93:7f:f0:64:2d:bb:e3:ba:f7:e1:6b:fd:f2:
                    aa:6b:91:1e:0f:50:52:86:1b:f7:5d:bd:f9:34:1d:
                    79:fc:7d:cc:5d:91:7e:2d:cb:46:1f:c4:06:be:b7:
                    9c:e5:b7:d2:ef:f6:82:b3:42:62:5a:07:26:c1:02:
                    7e:5f:f2:c7:a5:31:2a:0b:ba:e2:e1:14:6d:a3:02:
                    76:cf:42:46:00:e3:d5:d4:53:e8:e6:3d:39:1d:d5:
                    a3:33:87:05:a7:17:f5:5a:5d:a0:20:f1:25:91:c4:
                    b0:4c:05:f6:a7:74:f4:d8:a7:32:ab:2a:0e:5f:43:
                    1d:3c:aa:ae:5c:2c:00:ae:6a:a6:ca:22:2a:f1:ec:
                    d3:e2:e2:e6:81:de:f2:25:6a:b5:bf:44:e7:99:4c:
                    45:90:c6:f3:cc:b0:f7:2e:9c:6f:00:d6:16:1d:2c:
                    82:dd:a4:ea:4c:fb:59:ca:d4:57:d7:22:82:79:fa:
                    96:c2:7a:b0:06:e0:b9:88:8f:39:7c:50:51:db:0f:
                    f1:f9
                Exponent: 65537 (0x10001)
        Attributes:
        Requested Extensions:
            X509v3 Extended Key Usage: 
                TLS Web Client Authentication
    Signature Algorithm: sha256WithRSAEncryption
         44:8e:a6:bf:0a:a8:8e:c5:69:f5:da:2b:d7:c9:b2:5c:dd:61:
         74:29:97:f0:72:08:cd:49:f9:96:22:48:bc:c1:87:75:d0:29:
         7e:83:10:3d:a0:96:b0:24:8b:34:26:35:19:fb:4d:dd:ef:4d:
         14:45:1a:ec:45:17:6a:e1:c8:4c:8b:89:91:b5:61:71:6c:d3:
         19:41:4c:b2:83:14:a6:1e:83:0a:a3:d4:be:d4:0c:eb:40:f6:
         63:49:b8:99:2e:b8:59:df:2b:f1:08:78:1d:26:10:e9:5d:24:
         94:9d:1e:86:ce:bc:1e:c6:02:9c:0a:89:5a:a6:4e:23:84:55:
         4b:b6:80:3f:9e:73:dc:40:16:0f:5d:bb:37:5f:96:e3:d0:f8:
         30:26:66:f9:ed:26:2a:7f:94:4e:b9:c6:8a:86:ea:d2:2f:7f:
         66:7d:53:d7:e8:eb:30:b7:a4:1c:7e:be:d0:47:19:8b:57:12:
         3b:93:7f:38:5c:f4:ce:d2:ee:9b:9a:0b:e1:b3:f3:88:0c:79:
         9f:7a:2d:7b:80:94:50:d7:61:86:d2:1a:e4:31:b0:89:18:02:
         86:e9:6d:bf:12:91:4c:72:fa:0e:d9:f1:82:8b:6f:ce:4a:4f:
         d5:27:1f:22:9f:bc:76:f3:c3:d4:a7:b8:1c:88:94:0f:a0:48:
         82:8d:20:9d
-----BEGIN CERTIFICATE REQUEST-----
MIICpzCCAY8CAQAwPDEmMCQGA1UEAwwdcGljb0NURntyZWFkX215Y2VydF8xMmVi
YTdmMX0xEjAQBgNVBCkMCWN0ZlBsYXllcjCCASIwDQYJKoZIhvcNAQEBBQADggEP
ADCCAQoCggEBALpy6fpMuQHtDwrurMECVwArITyhZEWWOtGLTteR7QMx67dfVxm3
jEHlsrbVQtJBdMJDuMA3eRp14c3tD3GTf/BkLbvjuvfha/3yqmuRHg9QUoYb9129
+TQdefx9zF2Rfi3LRh/EBr63nOW30u/2grNCYloHJsECfl/yx6UxKgu64uEUbaMC
ds9CRgDj1dRT6OY9OR3VozOHBacX9VpdoCDxJZHEsEwF9qd09NinMqsqDl9DHTyq
rlwsAK5qpsoiKvHs0+Li5oHe8iVqtb9E55lMRZDG88yw9y6cbwDWFh0sgt2k6kz7
WcrUV9cignn6lsJ6sAbguYiPOXxQUdsP8fkCAwEAAaAmMCQGCSqGSIb3DQEJDjEX
MBUwEwYDVR0lBAwwCgYIKwYBBQUHAwIwDQYJKoZIhvcNAQELBQADggEBAESOpr8K
qI7FafXaK9fJslzdYXQpl/ByCM1J+ZYiSLzBh3XQKX6DED2glrAkizQmNRn7Td3v
TRRFGuxFF2rhyEyLiZG1YXFs0xlBTLKDFKYegwqj1L7UDOtA9mNJuJkuuFnfK/EI
eB0mEOldJJSdHobOvB7GApwKiVqmTiOEVUu2gD+ec9xAFg9duzdfluPQ+DAmZvnt
Jip/lE65xoqG6tIvf2Z9U9fo6zC3pBx+vtBHGYtXEjuTfzhc9M7S7puaC+Gz84gM
eZ96LXuAlFDXYYbSGuQxsIkYAobpbb8SkUxy+g7Z8YKLb85KT9UnHyKfvHbzw9Sn
uByIlA+gSIKNIJ0=
-----END CERTIFICATE REQUEST-----
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023]
└──╼ $

```


## Flag

``` picoCTF{read_mycert_12eba7f1} ```


## Notas adicionales

|Comando | Descripcion |
|------------ | ------------|
| openssl | herramienta que permite utilizar diversas funciones criptográficas de la biblioteca criptográfica de OpenSSL desde el shell |


## Referencias
+ [csr](https://www.dondominio.com/es/help/242/que-es-csr/)
+ [Decode with openssl](https://stackoverflow.com/questions/201070/how-to-decode-a-csr-file)
