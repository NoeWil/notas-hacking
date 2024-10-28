## Objetivo
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/9505cca05dc00fecead41106370ee619/VaultDoor5.java)

Hint
- You may find an encoder/decoder tool helpful, such as https://encoding.tools/
- Read the wikipedia articles on URL encoding and base 64 encoding to understand how they work and what the results look like.
## Solucion

Uso de cyberchef con formulas from base64 y urldecode

```
c0nv3rt1ng_fr0m_ba5e_64_84fd5095
```

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte1/vault-door-5]
└─$ java VaultDoor5
Enter vault password: picoCTF{c0nv3rt1ng_fr0m_ba5e_64_84fd5095}
Access granted.

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte1/vault-door-5]
└─$
```
## Notas adicionales
## Referencias
- [Código porciento - Wikipedia, la enciclopedia libre](https://es.wikipedia.org/wiki/C%C3%B3digo_porciento)