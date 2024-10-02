## Objetivo
Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png).

Hint
- What does meta mean in the context of files?
- Ever heard of metadata?
## Solucion

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/someta]
└─$ ls -la
total 116
drwxr-xr-x 2 wil wil   4096 Oct  2 10:37 .
drwxr-xr-x 4 wil wil   4096 Oct  2 10:37 ..
-rw-r--r-- 1 wil wil 108795 Oct 26  2020 pico_img.png

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/someta]
└─$ exiftool pico_img.png
ExifTool Version Number         : 12.76
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2020:10:26 12:38:23-06:00
File Access Date/Time           : 2024:10:02 10:38:57-06:00
File Inode Change Date/Time     : 2024:10:02 10:37:26-06:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Warning                         : [minor] Text/EXIF chunk(s) found after PNG IDAT (may be ignored by some readers)
Artist                          : picoCTF{s0_m3ta_d8944929}
Image Size                      : 600x600
Megapixels                      : 0.360

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/someta]
└─$
```

## Notas adicionales
## Referencias