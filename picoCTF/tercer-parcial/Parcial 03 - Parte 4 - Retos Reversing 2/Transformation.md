## Objetivo
I wonder what this really is... [enc](https://mercury.picoctf.net/static/0d3145dafdc4fbcf01891912eb6c0968/enc) `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`

## Solucion

```python
encoded_flag = open("enc").read()  
flag = ""  
for i in range(0, len(encoded_flag)):  
character1 = chr((ord(encoded_flag[i]) >> 8))  
character2 = chr(encoded_flag[i].encode('utf-16be')[-1])  
flag += character1  
flag += character2  
  
print("Flag: " + flag)
```

```bash
└─$ cat enc
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸弲㘶㠴挲ぽ
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2/transformation]
└─$ python3 flag.py
Flag: picoCTF{16_bits_inst34d_of_8_26684c20}

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2/transformation]
└─$

```
## Notas adicionales
## Referencias