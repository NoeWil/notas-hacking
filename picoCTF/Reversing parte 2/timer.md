## Objetivo
You will find the flag after analysing this apkDownload [here](https://artifacts.picoctf.net/c/449/timer.apk).

Hints
- Decompile
- mobsf or jadx

## Solucion

``` bash

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-2/timer]
└─$ unzip timer.apk
Archive:  timer.apk
replace META-INF/com/android/build/gradle/app-metadata.properties? [y]es, [n]o, [A]ll, [N]one, [r]ename: ^C
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-2/timer]
└─$ grep -r picoCTF
grep: classes3.dex: binary file matches

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-2/timer]
└─$ find . -name classes3.dex
./classes3.dex

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-2/timer]
└─$ strings classes3.dex | grep picoCTF
*picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}
```
## Solucion 2

Se puede utilizar jadx-gui para buscar la bandera con el indexador que tiene.

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-2/timer]
└─$ sudo apt install jadx
jadx is already the newest version (1.5.0-0kali2).
Summary:
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 0

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-2/timer]
└─$ jadx-gui
```
## Notas adicionales
## Referencias