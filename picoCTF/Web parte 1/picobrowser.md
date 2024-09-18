## Objetivo
This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/28921/` ([link](https://jupiter.challenges.picoctf.org/problem/28921/)) or http://jupiter.challenges.picoctf.org:28921

Hints
You don't need to download a new web browser
## Solucion
Modificamos el user agent para hacer creer que somos picobrowser
``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$ curl -s https://jupiter.challenges.picoctf.org/problem/28921/flag -H 'User-Agent: picobrowser' | grep picoCTF
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}</code></p>

┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$

```
## Notas adicionales
## Referencias