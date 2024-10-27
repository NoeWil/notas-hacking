## Objetivo
Download this packet capture and find the flag.

- [Download packet capture](https://artifacts.picoctf.net/c/134/capture.flag.pcap)
Hint
- All we know is that this packet capture includes a chat conversation and a file transfer.
## Solucion

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/parcial2/forensic1/eavesdrop]
└─$ openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/parcial2/forensic1/eavesdrop]
└─$ cat file.txt
picoCTF{nc_73115_411_dd54ab67}
┌──(wil㉿DESKTOP-FKOIV
```
## Notas adicionales
## Referencias