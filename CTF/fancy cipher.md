## Objetivo
Caesar isn't the only guy who can create good ciphers, mine is more fancy.

 [fancy-cipher.py](https://ctfd.anuies.mx/files/2f058e286647177b326e1e929507943a/fancy-cipher.py?token=eyJ1c2VyX2lkIjozNTksInRlYW1faWQiOjIxNywiZmlsZV9pZCI6OX0.Zw8hqQ.v0UJc_fq5NhAo0yLgbFpRGdxeM0 "fancy-cipher.py")

## Solucion
```python
encoded_text = '-3(.4?B,5*9@7;065&0:&:6&-(5*@D'

def decode(encoded_data, shift):
    dec = ''
    for _ in encoded_data:
        dec += chr((ord(_) - shift) % 0xff)
    return dec

for shift in range(256):
    decoded_flag = decode(encoded_text, shift)
    
    if all(32 <= ord(char) <= 126 for char in decoded_flag):
        print(f"Shift {shift}: {decoded_flag}")
```

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/fancy]
└─$ python3 flag.py | grep flagmx
Shift 198: flagmx{encryption_is_so_fancy}
```
## Notas adicionales
## Referencias