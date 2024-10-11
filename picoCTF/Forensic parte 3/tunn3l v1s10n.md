## Objetivo
We found this [file](https://mercury.picoctf.net/static/06a5e4ab22ba52cd66a038d51a6cc07b/tunn3l_v1s10n). Recover the flag.
Hints
- Weird that it won't display right...
## Solucion

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/tunnelvision]
└─$ file tunn3l_v1s10n
┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/tunnelvision]
└─$ file tunn3l_v1s10n
tunn3l_v1s10n: PC bitmap, Windows 3.x format, 1134 x 1338 x 24, image size 2893400, resolution 5669 x 5669 px/m, cbSize 2893454, bits offset 40

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/tunnelvision]
└─$ exiftool tunn3l_v1s10n
ExifTool Version Number         : 12.76
File Name                       : tunn3l_v1s10n
Directory                       : .
File Size                       : 2.9 MB
File Modification Date/Time     : 2024:10:09 10:39:59-06:00
File Access Date/Time           : 2024:10:09 10:40:03-06:00
File Inode Change Date/Time     : 2024:10:09 10:39:59-06:00
File Permissions                : -rw-r--r--
File Type                       : BMP
File Type Extension             : bmp
MIME Type                       : image/bmp
BMP Version                     : Windows V3
Image Width                     : 1134
Image Height                    : 1338
Planes                          : 1
Bit Depth                       : 24
Compression                     : None
Image Length                    : 2893400
Pixels Per Meter X              : 5669
Pixels Per Meter Y              : 5669
Num Colors                      : Use BitDepth
Num Important Colors            : All
Image Size                      : 1134x1338
Megapixels                      : 1.5

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/tunnelvision]
└─$ hexeditor tunn3l_v1s10n

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/tunnelvision]
└─$ eog tunn3l_v1s10n
```

## Notas adicionales
## Referencias
- [BMP file format - Wikipedia](https://en.wikipedia.org/wiki/BMP_file_format)
- [List of file signatures - Wikipedia](https://en.wikipedia.org/wiki/List_of_file_signatures)