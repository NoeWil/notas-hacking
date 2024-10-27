## Objetivo
The developer of this website mistakenly left an important artifact in the website source, can you find it?The website is [here](http://saturn.picoctf.net:64297/)

Hint
- How could you mirror the website on your local machine so you could use more powerful tools for searching?
## Solucion

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/parcial2/searchresulto]
└─$ ls
saturn.picoctf.net:57739

┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/parcial2/searchresulto]
└─$ grep -r 'picoCTF'
saturn.picoctf.net:57739/css/style.css:/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_587d12b8} **/

┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/parcial2/searchresulto]
└─$

```

## Notas adicionales
## Referencias