## Objetivo
This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/ff2585f7afd21b81f69d2fbe37c081ae/VaultDoor1.java)

Hint
- Look up the charAt() method online.
## Solucion

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte1/vault-door-1]
└─$ cat flag | sort | awk '{print($3)}' | tr -d "'" | tr -d "\n"
d35cr4mbl3_tH3_cH4r4cT3r5_75092e
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte1/vault-door-1]
└─$ javac
flag             VaultDoor1.java
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte1/vault-door-1]
└─$ javac VaultDoor1.java

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte1/vault-door-1]
└─$ java
flag              VaultDoor1.class  VaultDoor1.java
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte1/vault-door-1]
└─$ java VaultDoor1
Enter vault password: picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_75092e}
Access granted.
```

## Notas adicionales
## Referencias