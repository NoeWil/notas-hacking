## Objetivo
We found a brand new type of encryption, can you break the secret code? (Wrap with picoCTF{}) `ihjghbjgjhfbhbfcfjflfjiifdfgffihfeigidfligigffihfjfhfhfhigfjfffjfeihihfdieieih` [new_caesar.py](https://mercury.picoctf.net/static/2fc43dd1a3718df7debf367b0e092831/new_caesar.py)

Hints
- How does the cipher work if the alphabet isn't 26 letters?
- Even though the letters are split up, the same paradigms still apply
## Solucion

```python
import string

LOWERCASE_OFFSET = ord("a")
ALPHABET = string.ascii_lowercase[:16]


def b16_decode(cipher):
    dec = ""
    for c in range(0, len(cipher), 2):
        # turn the two characters into one binary string
        b = ""
        b += "{0:04b}".format(ALPHABET.index(cipher[c]))
        b += "{0:04b}".format(ALPHABET.index(cipher[c + 1]))
        dec += chr(int(b, 2))

    # return
    return dec

def unshift(c, k):
    t1 = ord(c) - LOWERCASE_OFFSET
    t2 = ord(k) - LOWERCASE_OFFSET
    return ALPHABET[(t1 - t2) % len(ALPHABET)]


enc = "ihjghbjgjhfbhbfcfjflfjiifdfgffihfeigidfligigffihfjfhfhfhigfjfffjfeihihfdieieih"

# loop through all possible keys
for key in ALPHABET:
    s = ""

    for i, c in enumerate(enc):
        # unshift it based on key
        s += unshift(c, key[i % len(key)])

    s = b16_decode(s)

    print(s)
```

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/crypto-1/new-cesar]
└─$ python3 flags.py
qQqRY[YSVUT[UYWWWYUYTS
v`@`AHJHwBEDvCurJuuDvHFFFuHDHCvvBssv
et_tu?_0797f143e2da9dd3e7555d7372ee1bbe
TcNcd.N/&(&U #"T!SP(SS"T&$$$S&"&!TT QQT
CR=RS=DCBOBBCBCC@@C
321>112122??2
!01ûóõó"ýðÿ!þ -õ  ÿ!óñññ óÿóþ!!ý..!
/
/ ê
ëâäâìïîíäîâàààâîâíì
ùÙùÚÑÓÑÛÞÝÜÓÝÑßßßÑÝÑÜÛ
ÈèÉÀÂÀÿÊÍÌþËýúÂýýÌþÀÎÎÎýÀÌÀËþþÊûûþ
íü×üý·×¸¿±¿î¹¼»íºìé±ìì»í¿½½½ì¿»¿ºíí¹êêí
ÜëÆëì¦Æ§® ®Ý¨«ªÜ©ÛØ ÛÛªÜ®¬¬¬Û®ª®©ÜÜ¨ÙÙÜ
ËÚµÚÛµÌËÊÇÊÊËËËÈÈË
ºÉ¤ÉÊ¤»º¹¶¹¹º¹ºº··º
©¸¸¹st{}{ªuxw©v¨¥}¨¨w©{yyy¨{w{v©©u¦¦©
§§¨bcjljdgfelfjhhhjfjed
```

Escogemos la que mas se parece a una posible bandera
```
picoCTF{et_tu?_0797f143e2da9dd3e7555d7372ee1bbe}
```
## Notas adicionales
## Referencias