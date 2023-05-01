# Local Authority

## Objetivo.

Can you get the flag?Go to this [website](http://saturn.picoctf.net:51108/) and see what you can discover.

## Solución.

**Abrimos la página que nos proporciona el reto**

Intentamos logear a la página e inspeccionamos el código fuente de esta, para acceder al script de js.

```
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```

Aqui se muestran los datos de acceso a la página, si ingresamos esos datos obtenemos la bandera.

**Bandera** picoCTF{j5_15_7r4n5p4r3n7_05df90c8}

## Notas opcionales.

## Referencias.

**Vídeo**

https://www.youtube.com/watch?v=Tm0pLRN55XQ&ab_channel=AlmondForce