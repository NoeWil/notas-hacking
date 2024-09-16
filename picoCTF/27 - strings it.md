## Objetivo
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?
## Solucion
```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.g0ZHIeDEng]
└─$ ls
strings

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.g0ZHIeDEng]
└─$ file strings
strings: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=0cdedfba33422d235dba8c90e00fb77b235f1ff8, not stripped

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.g0ZHIeDEng]
└─$ strings strings | grep pico
picoCTF{5tRIng5_1T_7f766a23}

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.g0ZHIeDEng]
└─$
```
## Notas adicionales
## Referencias