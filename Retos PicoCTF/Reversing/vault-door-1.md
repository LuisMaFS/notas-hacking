# vault-door-1

## Objetivo.

This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/87e103a8db01087de9ccf5a7a022ddf8/VaultDoor1.java)

## Solución.

**Descargar el archivo java del reto** 

┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor1]

└─$ wget https://jupiter.challenges.picoctf.org/static/87e103a8db01087de9ccf5a7a022ddf8/VaultDoor1.java 

**Hacer un cat para ver el código fuente**

┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor1]

└─$ cat VaultDoor1.java  

```
import java.util.*;

class VaultDoor1 {
    public static void main(String args[]) {
        VaultDoor1 vaultDoor = new VaultDoor1();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    // I came up with a more secure way to check the password without putting
    // the password itself in the source code. I think this is going to be
    // UNHACKABLE!! I hope Dr. Evil agrees...
    //
    // -Minion #8728
    public boolean checkPassword(String password) {
        return password.length() == 32 &&
               password.charAt(0)  == 'd' &&
               password.charAt(29) == 'a' &&
               password.charAt(4)  == 'r' &&
               password.charAt(2)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(3)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(1)  == '3' &&
               password.charAt(7)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(5)  == '4' &&
               password.charAt(9)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(8)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(6)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == '6' &&
               password.charAt(30) == 'f' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == 'd' &&
               password.charAt(26) == 'f' &&
               password.charAt(31) == '4';
    }
}
   
```

El códifo es una especie de login, el cual nos pide una contraseña única empieza con "picoCTF{" y termina con "}". La contraseña también la muestra como en el reto pasado, pero esta desordenada. Hay que ordenar la contraseña.

Así que ahora copiamos la contraseña y la pegamos en un archivo nano.

``` password.length() == 32 &&
               password.charAt(0)  == 'd' &&
               password.charAt(29) == 'a' &&
               password.charAt(4)  == 'r' &&
               password.charAt(2)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(3)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(1)  == '3' &&
               password.charAt(7)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(5)  == '4' &&
               password.charAt(9)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(8)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(6)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == '6' &&
               password.charAt(30) == 'f' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == 'd' &&
               password.charAt(26) == 'f' &&
               password.charAt(31) == '4'
   
```

**Sí ejecutamos esta línea, nos mostrará la tercer columna, sin comillas simples y sin espacios.**

┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor1]

└─$ cat labandera | sort | awk '{print($3)}' | tr -d "'" | tr -d "\n"

d35cr4mbl3_tH3_cH4r4cT3r5_f6daf432 

**Compilamos el programa**

┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor1]

└─$ javac VaultDoor1.java

Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true

**Abrimos el archivo .class este nos pedirá la contraseña**

┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor1]

└─$ java VaultDoor1 
```
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_f6daf4}
Access granted.
```

La contraseña es la llave.

**Bandera** picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_f6daf4}

## Notas opcionales.

## Referencias.

Vídeo

https://www.youtube.com/watch?v=QZ1ttEjyKxY&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=47&ab_channel=hackadvisermx