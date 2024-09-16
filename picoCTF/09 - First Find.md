## Objetivo
Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/502/files.zip)
## Solucion
```bash
──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.HgpymilDmD]
└─$ grep -r "pico"
grep: files.zip: binary file matches
files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt:picoCTF{f1nd_15_f457_ab443fd1}
files/14789.txt.utf-8:brassa un picotin d'orge_. Comme depuis une demi-heure environ c'était

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.HgpymilDmD]
└─$
```

### Solucion 2

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.HgpymilDmD]
└─$ find files -name "uber-secret.txt"
files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.HgpymilDmD]
└─$ cat files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
picoCTF{f1nd_15_f457_ab443fd1}

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.HgpymilDmD]
└─$
```
## Notas adicionales
## Referencias