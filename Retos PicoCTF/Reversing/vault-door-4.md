# vault-door-4

## Objetivo.

This vault uses ASCII encoding for the password. The source code for this vault is here: [VaultDoor4.java](https://jupiter.challenges.picoctf.org/static/834acd392e0964a41f05790655a994b9/VaultDoor4.java)

## Solución.

**Descargar el archivo java del reto** 

┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor4]

└─$ wget https://jupiter.challenges.picoctf.org/static/834acd392e0964a41f05790655a994b9/VaultDoor4.java

**Hacer un cat para ver el código fuente**

┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor4]

└─$ cat VaultDoor4.java  

```
import java.util.*;

class VaultDoor4 {
    public static void main(String args[]) {
        VaultDoor4 vaultDoor = new VaultDoor4();
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

    // I made myself dizzy converting all of these numbers into different bases,
    // so I just *know* that this vault will be impenetrable. This will make Dr.
    // Evil like me better than all of the other minions--especially Minion
    // #5620--I just know it!
    //
    //  .:::.   .:::.
    // :::::::.:::::::
    // :::::::::::::::
    // ':::::::::::::'
    //   ':::::::::'
    //     ':::::'
    //       ':'
    // -Minion #7781
    public boolean checkPassword(String password) {
        byte[] passBytes = password.getBytes();
        byte[] myBytes = {
            106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
            0142, 0131, 0164, 063 , 0163, 0137, 0146, 064 ,
            'a' , '8' , 'c' , 'd' , '8' , 'f' , '7' , 'e' ,
        };
        for (int i=0; i<32; i++) {
            if (passBytes[i] != myBytes[i]) {
                return false;
            }
        }
        return true;
    }
}
```

El código es una especie de login, el cual nos pide una contraseña única cuando el programa se ejecute. La contraseña esta en octal, hexadecimal, decimal y ASCII como codificación. 

**Podemos ayudarnos de javascriptt para obtener la contraseña**

```
String.fromCharCode(106 , 85 , 53 , 116 , 95 , 52 , 95 , 98 , 0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f, 0142, 0131, 0164, 063 , 0163, 0137, 0146, 064)

'jU5t_4_bUnCh_0f_bYt3s_f4'

String.fromCharCode(106 , 85 , 53 , 116 , 95 , 52 , 95 , 98 , 0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f, 0142, 0131, 0164, 063 , 0163, 0137, 0146, 064) + ['a' , '8' , 'c' , 'd' , '8' , 'f' , '7' , 'e']

'jU5t_4_bUnCh_0f_bYt3s_f4a,8,c,d,8,f,7,e'

String.fromCharCode(106 , 85 , 53 , 116 , 95 , 52 , 95 , 98 , 0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f, 0142, 0131, 0164, 063 , 0163, 0137, 0146, 064) + ['a' , '8' , 'c' , 'd' , '8' , 'f' , '7' , 'e'].join('')

'jU5t_4_bUnCh_0f_bYt3s_f4a8cd8f7e'

```


**Nos regresa la contraseña arreglada**

'jU5t_4_bUnCh_0f_bYt3s_f4a8cd8f7e'

**Compilamos el programa**

┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor4]

└─$ javac VaultDoor4.java

Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true

**Abrimos el archivo .class este nos pedirá la contraseña**

┌──(kali㉿kali)-[~/picoctf/reversing/vaultdoor4]

└─$ java VaultDoor3     
```
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{jU5t_4_bUnCh_0f_bYt3s_f4a8cd8f7e}
Access granted.
```

La contraseña es la llave.

**Bandera** picoCTF{jU5t_4_bUnCh_0f_bYt3s_f4a8cd8f7e}

## Notas opcionales.

## Referencias.

Vídeo

https://www.youtube.com/watch?v=B5y2spPIXj0&t=186s&ab_channel=hackadvisermx