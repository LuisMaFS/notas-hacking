## Descripción
You will find the flag after analysing this apk Download [here](https://artifacts.picoctf.net/c/421/timer.apk).

## Hints

+ Decompile
+ mobsf or jadx

## Solución
``` bash
┌─[✗]─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/timer]
└──╼ $d2j-dex2jar timer.apk
dex2jar timer.apk -> ./timer-dex2jar.jar
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/timer]
└──╼ $ls
timer  timer.apk  timer-dex2jar.jar  timer.md
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/timer]
└──╼ $jd-gui 
``` 


com/example.timer/BuildConfig.class
``` java
package com.example.timer;

public final class BuildConfig {
  public static final String APPLICATION_ID = "com.example.timer";
  
  public static final String BUILD_TYPE = "debug";
  
  public static final boolean DEBUG = Boolean.parseBoolean("true");
  
  public static final int VERSION_CODE = 1;
  
  public static final String VERSION_NAME = "picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}";
}

```


## Flag

``` picoCTF{t1m3r_r3v3rs3d_succ355fully_17496} ```


## Notas adicionales

|Comando | Descripcion |
|------------ | ------------|
| d2j-dex2jar | instrumento que convierte archivos .dex a archivos jar |

Una vez convertido a .jar con jd-gui entramos al buildconfig.class para observar el codigo 

## Referencias
+ [dex2jar](https://www.briskinfosec.com/tooloftheday/toolofthedaydetail/Dex2Jar)
