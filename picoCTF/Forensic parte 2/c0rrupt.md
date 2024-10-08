## Objetivo
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

Hint
- Try fixing the file header
## Solucion

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/c0rrupt]
└─$ hexeditor flag.png

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/c0rrupt]
└─$ pngcheck flag.png
zlib warning:  different version (expected 1.2.13, using 1.3.1)

flag.png  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERROR: flag.png

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/c0rrupt]
└─$ hexeditor flag.png

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/c0rrupt]
└─$ pngcheck -v flag.png
zlib warning:  different version (expected 1.2.13, using 1.3.1)

File: flag.png (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERRORS DETECTED in flag.png

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/c0rrupt]
└─$ hexeditor flag.png

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/c0rrupt]
└─$ pngcheck -v flag.png
zlib warning:  different version (expected 1.2.13, using 1.3.1)

File: flag.png (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
:  invalid chunk length (too large)
ERRORS DETECTED in flag.png

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/c0rrupt]
└─$ hexeditor flag.png

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/c0rrupt]
└─$ pngcheck -v flag.png
zlib warning:  different version (expected 1.2.13, using 1.3.1)

File: flag.png (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  invalid chunk name "DET" (ffffffab 44 45 54)
ERRORS DETECTED in flag.png

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/c0rrupt]
└─$ hexeditor flag.png

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/c0rrupt]
└─$ pngcheck -v flag.png
zlib warning:  different version (expected 1.2.13, using 1.3.1)

File: flag.png (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  chunk IDAT at offset 0x00057, length 65445
    zlib: deflated, 32K window, fast compression
  chunk IDAT at offset 0x10008, length 65524
  chunk IDAT at offset 0x20008, length 65524
  chunk IDAT at offset 0x30008, length 6304
  chunk IEND at offset 0x318b4, length 0
No errors detected in flag.png (9 chunks, 96.3% compression).
```

## Notas adicionales
## Referencias
- [List of file signatures - Wikipedia](https://en.wikipedia.org/wiki/List_of_file_signatures)
- [PNG - Wikipedia](https://en.wikipedia.org/wiki/PNG)