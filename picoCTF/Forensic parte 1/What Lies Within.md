## Objetivo
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?

Hint
- There is data encoded somewhere... there might be an online decoder.
## Solucion

Uso de decoder online de esteganografía.

## Solucion 2

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/whatlieswithin]
└─$ sudo gem install zsteg
Successfully installed zsteg-0.2.13
Parsing documentation for zsteg-0.2.13
Done installing documentation for zsteg after 0 seconds
1 gem installed

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/whatlieswithin]
└─$ zsteg -a buildings.png | grep pico
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
```

## Notas adicionales
## Referencias
- [Esteganografía - Wikipedia, la enciclopedia libre](https://es.wikipedia.org/wiki/Esteganograf%C3%ADa)