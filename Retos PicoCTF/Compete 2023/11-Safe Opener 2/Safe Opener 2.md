## Descripción
What can you do with this file? I forgot the key to my safe but this [file](https://artifacts.picoctf.net/c/314/SafeOpener.class) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?

## Hints

+ Download and try to decompile the file.

## Solución
``` bash

┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/Safe Opener 2]
└──╼ $strings SafeOpener.class 
<init>
Code
LineNumberTable
LocalVariableTable
this
LSafeOpener;
main
([Ljava/lang/String;)V
isOpen
args
[Ljava/lang/String;
keyboard
Ljava/io/BufferedReader;
encoder
Encoder
InnerClasses
Ljava/util/Base64$Encoder;
encodedkey
Ljava/lang/String;
StackMapTable
Exceptions
openSafe
(Ljava/lang/String;)Z
password
SourceFile
SafeOpener.java
java/io/BufferedReader
java/io/InputStreamReader
Enter password for the safe: 
java/lang/StringBuilder
You have  
 attempt(s) left
,picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_a230d237}
Sesame open
Password is incorrect
SafeOpener
java/lang/Object
java/util/Base64$Encoder
java/lang/String
java/io/IOException
java/lang/System
Ljava/io/InputStream;
(Ljava/io/InputStream;)V
(Ljava/io/Reader;)V
java/util/Base64
getEncoder
()Ljava/util/Base64$Encoder;
Ljava/io/PrintStream;
java/io/PrintStream
print
(Ljava/lang/String;)V
readLine
()Ljava/lang/String;
getBytes
()[B
encodeToString
([B)Ljava/lang/String;
println
append
-(Ljava/lang/String;)Ljava/lang/StringBuilder;
(I)Ljava/lang/StringBuilder;
toString
equals
(Ljava/lang/Object;)Z
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/Safe Opener 2]
└──╼ $strings SafeOpener.class | grep 'pico'
,picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_a230d237}
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/Safe Opener 2]
└──╼ $
```


OTRA SOLUCION CON "jd-gui"
``` bash
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/Safe Opener 2]
└──╼ $ls 
'Safe Opener 2.md'   SafeOpener.class
┌─[ramdark@parrot]─[~/Documents/Hacking_Notes_RFC/PicoCTF2023/Safe Opener 2]
└──╼ $jd-gui

```

``` java
import java.util.Base64;

public class SafeOpener {
  public static void main(String[] args) throws IOException {
    BufferedReader keyboard = new BufferedReader(new InputStreamReader(System.in));
    Base64.Encoder encoder = Base64.getEncoder();
    String encodedkey = "";
    String key = "";
    int i = 0;


    
    while (i < 3) {
      System.out.print("Enter password for the safe: ");
      key = keyboard.readLine();
      
      encodedkey = encoder.encodeToString(key.getBytes());
      System.out.println(encodedkey);
      
      boolean isOpen = openSafe(encodedkey);
      if (!isOpen) {
        System.out.println("You have  " + (2 - i) + " attempt(s) left");
        i++;
      } 
    } 
  }


  
  public static boolean openSafe(String password) {
    String encodedkey = "picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_a230d237}";
    
    if (password.equals(encodedkey)) {
      System.out.println("Sesame open");
      return true;
    } 
    
    System.out.println("Password is incorrect\n");
    return false;
  }
}
```


## Flag

``` picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_a230d237} ```


## Notas adicionales

|Comando | Descripcion |
|------------ | ------------|
| jd-gui | funcion básica en linux que permite ver el codigo en un java.class |


## Referencias
+ [jd-gui](https://www.kali.org/tools/jd-gui/)