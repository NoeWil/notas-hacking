## Objetivo
This image passes LSB statistical analysis, but we can't help but think there must be something to the visual artifacts present in this image...Download the image [here](https://artifacts.picoctf.net/c/306/Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png)

Hint
- What's causing the 'corruption' of the image?
## Solucion

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/parcial2/forensic1/MSB]
└─$ wget https://raw.githubusercontent.com/Pulho/sigBits/master/sigBits.py
--2024-10-26 20:58:33--  https://raw.githubusercontent.com/Pulho/sigBits/master/sigBits.py
Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 185.199.111.133, 185.199.108.133, 185.199.109.133, ...
Connecting to raw.githubusercontent.com (raw.githubusercontent.com)|185.199.111.133|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 7008 (6.8K) [text/plain]
Saving to: ‘sigBits.py’

sigBits.py           100%[=====================>]   6.84K  --.-KB/s    in 0s

2024-10-26 20:58:34 (45.7 MB/s) - ‘sigBits.py’ saved [7008/7008]


┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/parcial2/forensic1/MSB]
└─$ python3 sigBits.py -t=msb Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png
Done, check the output file!

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/parcial2/forensic1/MSB]
└─$ cat outputSB.txt | grep -o -E "picoCTF.{0,50}"
picoCTF{15_y0ur_que57_qu1x071c_0r_h3r01c_06326238}"Thou h

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/parcial2/forensic1/MSB]
└─$
```
## Notas adicionales
## Referencias