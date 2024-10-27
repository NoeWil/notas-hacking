## Objetivo
I don't like scrolling down to read the code of my website, so I've squished it. As a bonus, my pages load faster!Browse [here](http://titan.picoctf.net:50573/), and find the flag!

Hints
- Try CTRL+U / ⌘+U in your browser to view the page source. You can also add 'view-source:' before the URL, or try `curl <URL>` in your shell.
- Minification reduces the size of code, but does not change its functionality.
- What tools do developers use when working on a website? Many text editors and browsers include formatting.

## Solucion

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$ curl -s http://titan.picoctf.net:50573/ | grep -oE picoCTF{.*} --color=none | cut -d "\"" -f1
picoCTF{pr3tty_c0d3_d9c45a0b}

┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$
```

## Notas adicionales
## Referencias