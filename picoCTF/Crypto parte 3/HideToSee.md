## Objetivo
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/236/atbash.jpg).
Hint
- Download the image and try to extract it.

## Solucion

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/crypto/hidetosee]
└─$ steghide --extract -sf atbash.jpg
Enter passphrase:
wrote extracted data to "encrypted.txt".

┌──(wil㉿DESKTOP-FKOIV4I)-[~/crypto/hidetosee]
└─$ cat encrypted.txt
krxlXGU{zgyzhs_xizxp_zx751vx6}

┌──(wil㉿DESKTOP-FKOIV4I)-[~/crypto/hidetosee]
└─$
```

Uso de cyberchef con la formula atbash cipher
## Notas adicionales
## Referencias