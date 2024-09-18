## Objetivo
Someone's commits seems to be preventing the program from working. Who is it?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/72/challenge.zip)
## Solucion
``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.AgzarFuIYC]
└─$ cd
challenge.zip  drop-in/
┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.AgzarFuIYC]
└─$ cd drop-in/

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.AgzarFuIYC/drop-in]
└─$ ls
message.py

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.AgzarFuIYC/drop-in]
└─$ git log message.py
commit 9ae3e1bc67ad0143c611c5f65399b79850d20983
Author: picoCTF{@sk_th3_1nt3rn_b64c4705} <ops@picoctf.com>
Date:   Sat Mar 9 21:09:01 2024 +0000

    optimize file size of prod code

commit f3cec26cf7f80f91b5c3d1972f14dd4e9f97ec83
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:01 2024 +0000

    create top secret project

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.AgzarFuIYC/drop-in]
└─$
```
## Notas adicionales
## Referencias
- [The CTF Primer (picoctf.org)](https://primer.picoctf.org/#_git_version_control)

