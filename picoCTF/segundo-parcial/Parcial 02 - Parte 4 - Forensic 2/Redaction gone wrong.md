## Objetivo
Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

Hint
- How can you be sure of the redaction?
## Solucion

```
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/parcial2/forensic2/redaction]
└─$ pdftotext Financial_Report_for_ABC_Labs.pdf

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/parcial2/forensic2/redaction]
└─$ cat Financial_Report_for_ABC_Labs.txt
Financial Report for ABC Labs, Kigali, Rwanda for the year 2021.
Breakdown - Just painted over in MS word.

Cost Benefit Analysis
Credit Debit
This is not the flag, keep looking
Expenses from the
picoCTF{C4n_Y0u_S33_m3_fully}
Redacted document.

```

## Notas adicionales
## Referencias