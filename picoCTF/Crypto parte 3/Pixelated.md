## Objetivo
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled2.png)
Hints
- [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
- Think of different ways you can "stack" images

## Solucion
```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[/opt]
└─$ sudo wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar
[sudo] password for wil:
--2024-10-23 10:55:26--  http://www.caesum.com/handbook/Stegsolve.jar
Resolving www.caesum.com (www.caesum.com)... 216.234.165.33
Connecting to www.caesum.com (www.caesum.com)|216.234.165.33|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 312271 (305K) [application/x-java-archive]
Saving to: ‘stegsolve.jar’

stegsolve.jar        100%[=====================>] 304.95K  71.8KB/s    in 4.2s

2024-10-23 10:55:34 (71.8 KB/s) - ‘stegsolve.jar’ saved [312271/312271]


┌──(wil㉿DESKTOP-FKOIV4I)-[/opt]
└─$ sudo chmod +x stegsolve.jar

┌──(wil㉿DESKTOP-FKOIV4I)-[~/crypto/pixelated]
└─$ java -jar /opt/stegsolve.jar

┌──(wil㉿DESKTOP-FKOIV4I)-[~/crypto/pixelated]
└─$ eog flag.bmp
```

## Solucion 2

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/crypto/pixelated]
└─$ sudo apt install imagemagick
imagemagick is already the newest version (8:6.9.13.12+dfsg1-1).
Summary:
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 0

┌──(wil㉿DESKTOP-FKOIV4I)-[~/crypto/pixelated]
└─$ convert scrambled1.png scrambled2.png -compose Add -composite bandera.png

┌──(wil㉿DESKTOP-FKOIV4I)-[~/crypto/pixelated]
└─$ eog bandera.png
```

## Solucion 3
```python
from PIL import Image
import numpy as np

imagen1 = np.asarray(Image.open('scrambled1.png'))
imagen2 = np.asarray(Image.open('scrambled2.png'))

todo = imagen1 + imagen2

nuevaImagen = Image.fromarray(todo)

nuevaImagen.save('bandera2.png','PNG')
```

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/crypto/pixelated]
└─$ python3 exp.py

┌──(wil㉿DESKTOP-FKOIV4I)-[~/crypto/pixelated]
└─$ eog bandera2.png
```
## Notas adicionales
## Referencias