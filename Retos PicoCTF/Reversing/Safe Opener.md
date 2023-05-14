# Safe Opener

## Objetivo.

#### Description

Can you open this safe?I forgot the key to my safe but this [program](https://artifacts.picoctf.net/c/83/SafeOpener.java) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?Put the password you recover into the picoCTF flag format like:`picoCTF{password}`

## Solución.

**Descargar el archivo asm del reto** 

┌──(kali㉿kali)-[~/picoctf/reversing/safeopener]

└─$ wget https://artifacts.picoctf.net/c/83/SafeOpener.java

**Hacemos un cat para ver el contenido**

┌──(kali㉿kali)-[~/picoctf/reversing/safeopener]

└─$ cat Safe_Opener.java

```
import java.io.*;
import java.util.*;  
public class SafeOpener {
    public static void main(String args[]) throws IOException {
        BufferedReader keyboard = new BufferedReader(new InputStreamReader(System.in));
        Base64.Encoder encoder = Base64.getEncoder();
        String encodedkey = "";
        String key = "";
        int i = 0;
        boolean isOpen;
        

        while (i < 3) {
            System.out.print("Enter password for the safe: ");
            key = keyboard.readLine();

            encodedkey = encoder.encodeToString(key.getBytes());
            System.out.println(encodedkey);
              
            isOpen = openSafe(encodedkey);
            if (!isOpen) {
                System.out.println("You have  " + (2 - i) + " attempt(s) left");
                i++;
                continue;
            }
            break;
        }
    }
    
    public static boolean openSafe(String password) {
        String encodedkey = "cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz";
        
        if (password.equals(encodedkey)) {
            System.out.println("Sesame open");
            return true;
        }
        else {
            System.out.println("Password is incorrect\n");
            return false;
        }
    }
}
```

Se trata de un programa en Java.

**Ponemos atención a lo siguiente**

``` 
    public static boolean openSafe(String password) {
        String encodedkey = "cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz";
```

Aquí esta la contraseña y por ende la bandera.

**La convertimos a base 64**

┌──(kali㉿kali)-[~/picoctf/reversing/safeopener]

└─$ echo cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz | base64 -d

pl3as3_l3t_m3_1nt0_th3_saf3

**Bandera** picoCTF{pl3as3_l3t_m3_1nt0_th3_saf3}

## Notas opcionales.

## Referencias.

Vídeo

https://www.youtube.com/watch?v=A5UuCpFS0E8&ab_channel=AlmondForce