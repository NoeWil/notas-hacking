## Objetivo
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

Hint
- How do operating systems know what kind of file it is? (It's not just the ending!
- Make sure to submit the flag as picoCTF{XXXXX}
## Solucion

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/extensions]
└─$ file flag.txt
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/extensions]
└─$ mv flag.txt flag.png

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/extensions]
└─$ eog flag.png
```
## Notas adicionales
## Referencias
- [List of file signatures - Wikipedia](https://en.wikipedia.org/wiki/List_of_file_signatures)