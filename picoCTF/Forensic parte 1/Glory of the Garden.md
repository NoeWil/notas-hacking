## Objetivo
This [garden](https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg) contains more than it seems.

Hint
- What is a hex editor?
## Solucion

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/gloryofthegarden]
└─$ ls -la
total 2252
drwxr-xr-x 2 wil wil    4096 Oct  2 10:23 .
drwxr-xr-x 3 wil wil    4096 Oct  2 10:22 ..
-rw-r--r-- 1 wil wil 2295192 Oct 26  2020 garden.jpg

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/gloryofthegarden]
└─$ eog  garden.jpg

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/gloryofthegarden]
└─$ hexeditor garden.jpg

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/gloryofthegarden]
└─$
```
## Notas adicionales
## Referencias