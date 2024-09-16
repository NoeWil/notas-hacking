## Objetivo
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/71/challenge.zip)
## Solucion
``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.AgzarFuIYC/drop-in]
└─$ git branch
  feature/part-1
  feature/part-2
  feature/part-3
* main

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.AgzarFuIYC/drop-in]
└─$ git checkout feature/part-1
Switched to branch 'feature/part-1'

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.AgzarFuIYC/drop-in]
└─$ cat flag.py
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')
┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.AgzarFuIYC/drop-in]
└─$ git checkout feature/part-2
Switched to branch 'feature/part-2'

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.AgzarFuIYC/drop-in]
└─$ cat flag.py
print("Printing the flag...")

print("m@k3s_th3_dr3@m_", end='')
┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.AgzarFuIYC/drop-in]
└─$ git checkout feature/part-3
Switched to branch 'feature/part-3'

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.AgzarFuIYC/drop-in]
└─$ cat flag.py
print("Printing the flag...")

print("w0rk_4c24302f}")

```
## Notas adicionales
## Referencias
- [The CTF Primer (picoctf.org)](https://primer.picoctf.org/#_git_version_control)
