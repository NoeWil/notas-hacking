## Objetivo

## Solucion

```python
import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5a) + >

flag = str_xor(flag_enc, 'enkidu')
print('That is correct! Here\'s your flag: ' + flag)
```

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.HgpymilDmD]
└─$ nano fixme1.py

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.HgpymilDmD]
└─$ python3 fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}
```
## Notas adicionales
la identacion es importante en python.
## Referencias