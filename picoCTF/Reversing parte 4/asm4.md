## Objetivo
What will asm4("picoCTF_a3112") return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/80186ad81f4a1569b480e7fbf68b29ca/test.S)

Hint
- Treat the Array argument as a pointer

## Solucion

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-4/asm4]
└─$ cat test.S | cut -d ":" -f 2 > chal.s

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-4/asm4]
└─$ mousepad chal.s
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-4/asm4]
└─$ gcc -m32 -c chal.s -o chal.o

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-4/asm4]
└─$ ls
chal.o  chal.s  test.S

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-4/asm4]
└─$ chmod +x chal.o

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-4/asm4]
└─$ ls
chal.o  chal.s  test.S

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-4/asm4]
└─$ ./chal.o
-bash: ./chal.o: cannot execute binary file: Exec format error

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-4/asm4]
└─$ gcc -m32 -c solve.c -o solve.o -w -fpermissive

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-4/asm4]
└─$ ls
chal.o  chal.s  solve.c  solve.o  test.S

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-4/asm4]
└─$ gcc -m32 -o a.out chal.o solve.o
/usr/bin/ld: warning: chal.o: missing .note.GNU-stack section implies executable stack
/usr/bin/ld: NOTE: This behaviour is deprecated and will be removed in a future version of the linker

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-4/asm4]
└─$ ./a.out
flag: 0x1d0
```

## Notas adicionales
## Referencias
