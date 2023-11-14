
## Objetivo
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility. The source code for the training vault is here: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/a4a1ca9c54d8fac9404f9cbc50d9751a/VaultDoorTraining.java)
## Solución
```
┌──(kali㉿kali)-[~/vaultdoortraining]
└─$ cat VaultDoorTraining.java
import java.util.*;

class VaultDoorTraining {
    public static void main(String args[]) {
        VaultDoorTraining vaultDoor = new VaultDoorTraining();
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

    // The password is below. Is it safe to put the password in the source code?
    // What if somebody stole our source code? Then they would know what our
    // password is. Hmm... I will think of some ways to improve the security
    // on the other doors.
    //
    // -Minion #9567
    public boolean checkPassword(String password) {
        return password.equals("w4rm1ng_Up_w1tH_jAv4_be8d9806f18");
    }
}
                                                                           
┌──(kali㉿kali)-[~/vaultdoortraining]
└─$ javac VaultDoorTraining.java 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                                                           
┌──(kali㉿kali)-[~/vaultdoortraining]
└─$ ls -la
total 44
drwxr-xr-x  2 kali kali  4096 Nov 14 00:47 .
drwx------ 31 kali kali 32768 Nov 14 00:27 ..
-rw-r--r--  1 kali kali  1106 Nov 14 00:47 VaultDoorTraining.class
-rw-r--r--  1 kali kali   943 Oct 26  2020 VaultDoorTraining.java
                                                                           
┌──(kali㉿kali)-[~/vaultdoortraining]
└─$ java VaultDoorTraining      
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{w4rm1ng_Up_w1tH_jAv4_be8d9806f18}
Access granted.
                                                                           
┌──(kali㉿kali)-[~/vaultdoortraining]
└─$ 
```

## Notas adicionales
- Solo teniamos que compilar con javac VaultDoorTraining.java 
- Ejecutabamos con java VaultDoorTraining
- nos pedia una contraseña que viene en el archivo que descargamos, lo podemos visualizar con un cat.
- 