## Objetivo
Someone might have hidden the password in the trace file.Find the key to unlock [this file](https://artifacts.picoctf.net/c/498/flag.zip). [This tracefile](https://artifacts.picoctf.net/c/498/dump.pcap) might be good to analyze.

Hints
- Download the pcap and look for the password or flag.
- Don't try to use a password cracking tool, there are easier ways here.
## Solucion

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/parcial2/forensic1/FindAndOpen]
└─$ unzip flag.zip
Archive:  flag.zip
[flag.zip] flag password:
 extracting: flag

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/parcial2/forensic1/FindAndOpen]
└─$ ls
dump.pcap  flag  flag.zip

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/parcial2/forensic1/FindAndOpen]
└─$ cat flag
picoCTF{R34DING_LOKd_fil56_succ3ss_494c4f32}

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/parcial2/forensic1/FindAndOpen]
└─$
```
## Notas adicionales
## Referencias