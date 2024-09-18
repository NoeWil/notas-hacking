## Objetivo
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/static)? This [BASH script](https://mercury.picoctf.net/static/7495259e963bd5b67d0fb8b616652618/ltdis.sh) might help!
## Solucion

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.g0ZHIeDEng]
└─$ ls
ltdis.sh  static

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.g0ZHIeDEng]
└─$ file static
static: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=bedc412be2156b04706c1f2568fcff42306dea27, not stripped

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.g0ZHIeDEng]
└─$ strings static | grep  pico
picoCTF{d15a5m_t34s3r_f6c48608}
```
## Notas adicionales
## Referencias