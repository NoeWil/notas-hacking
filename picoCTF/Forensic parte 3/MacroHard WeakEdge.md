## Objetivo
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/52da699e0f203321c7c90ab56ea912d8/Forensics%20is%20fun.pptm)
## Solucion

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/macrohard]
└─$ file Forensics\ is\ fun.pptm
Forensics is fun.pptm: Microsoft PowerPoint 2007+

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/macrohard]
└─$ unzip Forensics\ is\ fun.pptm

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/macrohard]
└─$ cd ppt/slideMasters/

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/macrohard/ppt/slideMasters]
└─$ cat hidden
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/macrohard/ppt/slideMasters]
└─$ cat hidden | tr -d ' ' | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: invalid input


```

## Notas adicionales
## Referencias