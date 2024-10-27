## Objetivo
The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:59520/) out.

## Solucion

Ingresamos a:
- [saturn.picoctf.net:59520/robots.txt](http://saturn.picoctf.net:59520/robots.txt) Aqui obtendremos una linea en base 64 que nos guiara a la bandera.
- [saturn.picoctf.net:59520/js/myfile.txt](http://saturn.picoctf.net:59520/js/myfile.txt)

```
picoCTF{Who_D03sN7_L1k5_90B0T5_22ce1f22}
```

## Solucion 2

```bash

┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/parcial2/searchresulto]
└─$ curl http://saturn.picoctf.net:59520/ | grep -r 'picoCTF'
saturn.picoctf.net:57739/css/style.css:/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_587d12b8} **/
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0 15920    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
curl: (23) Failure writing output to destination, passed 11200 returned 0
```
## Notas adicionales
## Referencias