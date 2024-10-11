## Objetivo
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/f6cc2560a70b1ea811c151accba5390f/dolls.jpg)

Hints
- Wait, you can hide files inside files? But how do you find them?
- Make sure to submit the flag as picoCTF{XXXXX}

## Solucion

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/doll]
└─$ unzip dolls.jpg
Archive:  dolls.jpg
warning [dolls.jpg]:  272492 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/2_c.jpg

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/doll]
└─$ ls
base_images  dolls.jpg

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/doll]
└─$ cd
base_images/ dolls.jpg
┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/doll]
└─$ cd base_images/

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/doll/base_images]
└─$ unzip 2_c.jpg
Archive:  2_c.jpg
warning [2_c.jpg]:  187707 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/3_c.jpg

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/doll/base_images]
└─$ ls
2_c.jpg  base_images

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/doll/base_images]
└─$ cd base_images/

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/doll/base_images/base_images]
└─$ unzip 3_c.jpg
Archive:  3_c.jpg
warning [3_c.jpg]:  123606 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/4_c.jpg

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/doll/base_images/base_images]
└─$ ls
3_c.jpg  base_images

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/doll/base_images/base_images]
└─$ cd
3_c.jpg      base_images/
┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/doll/base_images/base_images]
└─$ cd base_images/

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/doll/base_images/base_images/base_images]
└─$ ls
4_c.jpg

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/doll/base_images/base_images/base_images]
└─$ unzip 4_c.jpg
Archive:  4_c.jpg
warning [4_c.jpg]:  79578 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: flag.txt

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/doll/base_images/base_images/base_images]
└─$ ls
4_c.jpg  flag.txt

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/doll/base_images/base_images/base_images]
└─$ cat flag.txt
picoCTF{ac0072c423ee13bfc0b166af72e25b61}
```

## Notas adicionales
## Referencias