## Objetivo
Can you get the flag?Reverse engineer this [binary](https://artifacts.picoctf.net/c/205/unpackme-upx).

Hint
- What is UPX?
## Solucion

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2/unpackme]
└─$
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2/unpackme]
└─$ ./unpackme-upx
What's my favorite number? 7
Sorry, that's not it!

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2/unpackme]
└─$ strings unpackme-upx | grep pico

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2/unpackme]
└─$ upx -d unpackme-upx
                       Ultimate Packer for eXecutables
                          Copyright (C) 1996 - 2024
UPX 4.2.4       Markus Oberhumer, Laszlo Molnar & John Reiser    May 9th 2024

        File size         Ratio      Format      Name
   --------------------   ------   -----------   -----------
   1006445 <-    379188   37.68%   linux/amd64   unpackme-upx

Unpacked 1 file.

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2/unpackme]
└─$ ls
unpackme-upx

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2/unpackme]
└─$ ghidra

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2/unpackme]
└─$ ./unpackme-upx
What's my favorite number? 754635
picoCTF{up><_m3_f7w_5769b54e}
```

## Notas adicionales
## Referencias