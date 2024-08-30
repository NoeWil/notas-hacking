## Objetivo
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)
## Datos de acceso al nivel
* Username = bandit12
* password = 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
## Solucion
### Forma 1
````bash
bandit12@bandit:~$ xxd -r data.txt | file -
/dev/stdin: gzip compressed data, was "data2.bin", last modified: Wed Jul 17 15:57:06 2024, max compression, from Unix
bandit12@bandit:~$ mkdir /tmp/hmnwxd
bandit12@bandit:~$ xxd -r data.txt > /tmp/hmnwxd/data
bandit12@bandit:~$ cd /tmp/hmnwxd
bandit12@bandit:/tmp/hmnwxd$ ls
data
bandit12@bandit:/tmp/hmnwxd$ file data
data: gzip compressed data, was "data2.bin", last modified: Wed Jul 17 15:57:06 2024, max compression, from Unix, original size modulo 2^32 577
bandit12@bandit:/tmp/hmnwxd$ mv data data.gz
bandit12@bandit:/tmp/hmnwxd$ gzip -d data.gz
bandit12@bandit:/tmp/hmnwxd$ file data
data: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/hmnwxd$ mv data data.bz2
bandit12@bandit:/tmp/hmnwxd$ bzip2 -d data.bz2
bandit12@bandit:/tmp/hmnwxd$ ls
data
bandit12@bandit:/tmp/hmnwxd$ file data
data: gzip compressed data, was "data4.bin", last modified: Wed Jul 17 15:57:06 2024, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/hmnwxd$ mv data data.gz
bandit12@bandit:/tmp/hmnwxd$ gzip -d data.gz
bandit12@bandit:/tmp/hmnwxd$ ls
data
bandit12@bandit:/tmp/hmnwxd$ file data
data: POSIX tar archive (GNU)
bandit12@bandit:/tmp/hmnwxd$ mv data data.tar
bandit12@bandit:/tmp/hmnwxd$ xtables-
xtables-legacy-multi  xtables-monitor       xtables-nft-multi
bandit12@bandit:/tmp/hmnwxd$ tar x
xa  xb  xB  xC  xf  xF  xg  xG  xh  xH  xi  xI  xj  xJ  xk  xK  xl  xL  xm  xM  xn  xN  xo  xO  xp  xP  xR  xs  xS  xT  xU  xv  xV  xw  xW  xX  xz  xZ
bandit12@bandit:/tmp/hmnwxd$ tar xf data.tar
bandit12@bandit:/tmp/hmnwxd$ ls
data5.bin  data.tar
bandit12@bandit:/tmp/hmnwxd$ rm data.tar
bandit12@bandit:/tmp/hmnwxd$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/hmnwxd$ mv data5.bin data5.tr
bandit12@bandit:/tmp/hmnwxd$ ls
data5.tr
bandit12@bandit:/tmp/hmnwxd$ tar xf data5.tr
bandit12@bandit:/tmp/hmnwxd$ ls
data5.tr  data6.bin
bandit12@bandit:/tmp/hmnwxd$ rm data5.tr
bandit12@bandit:/tmp/hmnwxd$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ cd /tmp/hmnwxd
bandit12@bandit:/tmp/hmnwxd$ ls
data6.bin
bandit12@bandit:/tmp/hmnwxd$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/hmnwxd$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/hmnwxd$ bzip2 -d data6.bz2
bandit12@bandit:/tmp/hmnwxd$ ls
data6
bandit12@bandit:/tmp/hmnwxd$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/hmnwxd$ mv data6 data6.tr
bandit12@bandit:/tmp/hmnwxd$ tar xf data6.tr
bandit12@bandit:/tmp/hmnwxd$ ls
data6.tr  data8.bin
bandit12@bandit:/tmp/hmnwxd$ rm data6.tr
bandit12@bandit:/tmp/hmnwxd$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Wed Jul 17 15:57:06 2024, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/hmnwxd$ mv data8.bin data8.gz
bandit12@bandit:/tmp/hmnwxd$ gzip -d data8.gz
bandit12@bandit:/tmp/hmnwxd$ ls
data8
bandit12@bandit:/tmp/hmnwxd$ file data8
data8: ASCII text
bandit12@bandit:/tmp/hmnwxd$ cat data8
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
bandit12@bandit:/tmp/hmnwxd$
````
### Forma 2
``` bash

bandit12@bandit:~$ xxd -r data.txt | file -
/dev/stdin: gzip compressed data, was "data2.bin", last modified: Thu May 7 18:14:30 2020, max compression, from Unix
bandit12@bandit:~$
bandit12@bandit:~$
bandit12@bandit:~$ xxd -r data.txt | zcat |file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat |file -
/dev/stdin: gzip compressed data, was "data4.bin", last modified: Thu May 7 18:14:30 2020, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat |file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat |file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | file -
/dev/stdin: gzip compressed data, was "data9.bin", last modified: Thu May 7 18:14:30 2020, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat | file -
/dev/stdin: ASCII text
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```
## Notas adicionales
```
Algunos tipos de compresion en Linux
-----------------------------------------------------
ext comp desc ver en consola
-----------------------------------------------------
.gz gzip gzip -d (gunzip) zcat
.bz2 bzip2 bzip2 -d (bunzip2) bzcat
.tar tar tar xf tar xO
----------------------------------------------------

otros (instalar) :
.zip zip unzip (7z x)
.rar rar unrar (7z x)
```
## Referencias
[Hex dump on Wikipedia](https://en.wikipedia.org/wiki/Hex_dump)
