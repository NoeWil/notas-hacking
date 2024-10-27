## Objetivo
Download this image and find the flag.

- [Download image](https://artifacts.picoctf.net/c/216/pico.flag.png)

Hint
- We know the end sequence of the message will be `$t3g0`.

## Solucion

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/parcial2/forensic2/stego]
└─$ eog pico.flag.png

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/parcial2/forensic2/stego]
└─$ exiftool pico.flag.png
ExifTool Version Number         : 12.76
File Name                       : pico.flag.png
Directory                       : .
File Size                       : 13 kB
File Modification Date/Time     : 2023:08:04 14:36:17-06:00
File Access Date/Time           : 2024:10:26 22:21:35-06:00
File Inode Change Date/Time     : 2024:10:26 22:21:16-06:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 585
Image Height                    : 172
Bit Depth                       : 8
Color Type                      : RGB with Alpha
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Image Size                      : 585x172
Megapixels                      : 0.101

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/parcial2/forensic2/stego]
└─$ zsteg 2b pico.flag.png
[.] 2b
[!] #<Errno::ENOENT: No such file or directory @ rb_sysopen - 2b>

[.] pico.flag.png
b1,rgb,lsb,xy       .. text: "picoCTF{7h3r3_15_n0_5p00n_a1062667}$t3g0"
b1,abgr,lsb,xy      .. text: "E2A5q4E%uSA"
b2,b,lsb,xy         .. text: "AAPAAQTAAA"
b2,b,msb,xy         .. text: "HWUUUUUU"
b3,r,lsb,xy         .. file: gfxboot compiled html help file
b4,r,lsb,xy         .. file: Targa image data (16-273) 65536 x 4097 x 1 +4352 +4369 - 1-bit alpha - right "\021\020\001\001\021\021\001\001\021\021\001"
b4,g,lsb,xy         .. file: 0420 Alliant virtual executable not stripped
b4,b,lsb,xy         .. file: Targa image data - Map 272 x 17 x 16 +257 +272 - 1-bit alpha "\020\001\021\001\021\020\020\001\020\001\020\001"
b4,bgr,lsb,xy       .. file: Targa image data - Map 273 x 272 x 16 +1 +4113 - 1-bit alpha "\020\001\001\001"
b4,rgba,msb,xy      .. file: Applesoft BASIC program data, first line number 8
```

## Notas adicionales
## Referencias