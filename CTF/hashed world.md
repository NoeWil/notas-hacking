## Objetivo
To avoid leak the flag, I hashed it. Can you crack the hash and win the game? Keep it small and simple, take a closer look.

This challenge uses brute forcing, limit your max length, it works no matter the hardware being used.
## Solucion

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/hashed]
└─$ fcrackzip -v -u -l 1-6 small_r_good.zip\?token\=eyJ1c2VyX2lkIjozNTksInRlYW1faWQiOjIxNywiZmlsZV9pZCI6OH0.Zw76bA.EMHsgk6ss4ZhbwqolArPTnJhnxQ
found file 'made_unlike.txt', (size cp/uc    297/   499, flags 9, chk 4c30)
found file 'make_unlike.7z', (size cp/uc    348/   338, flags 9, chk 4d80)
checking pw C-H*~

PASSWORD FOUND!!!!: pw == C*z!7

┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/hashed]
└─$ unzip small_r_good.zip\?token\=eyJ1c2VyX2lkIjozNTksInRlYW1faWQiOjIxNywiZmlsZV9pZCI6OH0.Zw76bA.EMHsgk6ss4ZhbwqolArPTnJhnxQ
Archive:  small_r_good.zip?token=eyJ1c2VyX2lkIjozNTksInRlYW1faWQiOjIxNywiZmlsZV9pZCI6OH0.Zw76bA.EMHsgk6ss4ZhbwqolArPTnJhnxQ
[small_r_good.zip?token=eyJ1c2VyX2lkIjozNTksInRlYW1faWQiOjIxNywiZmlsZV9pZCI6OH0.Zw76bA.EMHsgk6ss4ZhbwqolArPTnJhnxQ] made_unlike.txt password:
  inflating: made_unlike.txt
  inflating: make_unlike.7z
┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/hashed]
└─$ ls -la
total 20
drwxr-xr-x 2 wil wil 4096 Oct 15 17:43  .
drwxr-xr-x 4 wil wil 4096 Oct 15 17:28  ..
-rw-r--r-- 1 wil wil  499 Jun 19 09:33  made_unlike.txt
-rw-r--r-- 1 wil wil  338 Jun 19 09:43  make_unlike.7z
-rw-r--r-- 1 wil wil 1013 Sep 24 11:23 'small_r_good.zip?token=eyJ1c2VyX2lkIjozNTksInRlYW1faWQiOjIxNywiZmlsZV9pZCI6OH0.Zw76bA.EMHsgk6ss4ZhbwqolArPTnJhnxQ'
┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/hashed]
└─$ hashcat -m 0 -a 0 made_unlike.txt /usr/share/wordlists/rockyou.txt
hashcat (v6.2.6) starting

OpenCL API (OpenCL 3.0 PoCL 6.0+debian  Linux, None+Asserts, RELOC, LLVM 17.0.6, SLEEF, DISTRO, POCL_DEBUG) - Platform #1 [The pocl project]
============================================================================================================================================
* Device #1: cpu-haswell-AMD A4-9125 RADEON R3, 4 COMPUTE CORES 2C+2G, 1252/2568 MB (512 MB allocatable), 2MCU

Minimum password length supported by kernel: 0
Maximum password length supported by kernel: 256

Hashfile 'made_unlike.txt' on line 4 (edfa12...05301ef06bc7f8bdf24c89c7cc768923): Token length exception
Hashfile 'made_unlike.txt' on line 5 (9d5e6de6e9432865dd6a5ded27682705d2a4ef1a): Token length exception
Hashfile 'made_unlike.txt' on line 6 (2db2f4ebd5241da27c2d83260481411daeb9d9a1): Token length exception
Hashfile 'made_unlike.txt' on line 7 (e58a5a...0e81da644136eb0e86754fbfa25fb3a0): Token length exception
Hashfile 'made_unlike.txt' on line 8 (bac389...dbdb645273e787b8a940cec5adac95f5): Token length exception
Hashfile 'made_unlike.txt' on line 9 (1ddd4b...264fb062142bbb7669d21c0d30ece2c6): Token length exception

* Token length exception: 6/9 hashes
  This error happens if the wrong hash type is specified, if the hashes are
  malformed, or if input is otherwise not as expected (for example, if the
  --username option is used but no username is present)

Hashes: 3 digests; 3 unique digests, 1 unique salts
Bitmaps: 16 bits, 65536 entries, 0x0000ffff mask, 262144 bytes, 5/13 rotates
Rules: 1

Optimizers applied:
* Zero-Byte
* Early-Skip
* Not-Salted
* Not-Iterated
* Single-Salt
* Raw-Hash

ATTENTION! Pure (unoptimized) backend kernels selected.
Pure kernels can crack longer passwords, but drastically reduce performance.
If you want to switch to optimized kernels, append -O to your commandline.
See the above message to find out about the exact limits.

Watchdog: Hardware monitoring interface not found on your system.
Watchdog: Temperature abort trigger disabled.

Host memory required for this attack: 0 MB

Dictionary cache built:
* Filename..: /usr/share/wordlists/rockyou.txt
* Passwords.: 14344392
* Bytes.....: 139921507
* Keyspace..: 14344385
* Runtime...: 4 secs

9a5a7f2bf1273ae46cf8181f47a0a02f:vivamexico
Approaching final keyspace - workload adjusted.


Session..........: hashcat
Status...........: Exhausted
Hash.Mode........: 0 (MD5)
Hash.Target......: made_unlike.txt
Time.Started.....: Tue Oct 15 18:12:14 2024 (17 secs)
Time.Estimated...: Tue Oct 15 18:12:31 2024 (0 secs)
Kernel.Feature...: Pure Kernel
Guess.Base.......: File (/usr/share/wordlists/rockyou.txt)
Guess.Queue......: 1/1 (100.00%)
Speed.#1.........:  1067.3 kH/s (0.16ms) @ Accel:256 Loops:1 Thr:1 Vec:8
Recovered........: 1/3 (33.33%) Digests (total), 1/3 (33.33%) Digests (new)
Progress.........: 14344385/14344385 (100.00%)
Rejected.........: 0/14344385 (0.00%)
Restore.Point....: 14344385/14344385 (100.00%)
Restore.Sub.#1...: Salt:0 Amplifier:0-1 Iteration:0-1
Candidate.Engine.: Device Generator
Candidates.#1....: $HEX[206b72697374656e616e6e65] -> $HEX[042a0337c2a156616d6f732103]

Started: Tue Oct 15 18:10:37 2024
Stopped: Tue Oct 15 18:12:32 2024
┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/hashed]
└─$ 7z x make_unlike.7z

7-Zip 24.07 (x64) : Copyright (c) 1999-2024 Igor Pavlov : 2024-06-19
 64-bit locale=en_US.UTF-8 Threads:2 OPEN_MAX:1024

Scanning the drive for archives:
1 file, 338 bytes (1 KiB)

Extracting archive: make_unlike.7z
--
Path = make_unlike.7z
Type = 7z
Physical Size = 338
Headers Size = 162
Method = LZMA2:12 7zAES
Solid = -
Blocks = 1


Enter password (will not be echoed):
Everything is Ok

Size:       225
Compressed: 338

┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/hashed]
└─$ ls -la
total 24
drwxr-xr-x 2 wil wil 4096 Oct 15 18:36  .
drwxr-xr-x 4 wil wil 4096 Oct 15 17:28  ..
-rw-r--r-- 1 wil wil  225 Jun 19 08:25  common_pass_rules.zip
-rw-r--r-- 1 wil wil  499 Jun 19 09:33  made_unlike.txt
-rw-r--r-- 1 wil wil  338 Jun 19 09:43  make_unlike.7z
-rw-r--r-- 1 wil wil 1013 Sep 24 11:23 'small_r_good.zip?token=eyJ1c2VyX2lkIjozNTksInRlYW1faWQiOjIxNywiZmlsZV9pZCI6OH0.Zw8KWg.PJ2fP1ZR5CcmV6tLlvrBIboXQKs'

──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/hashed]
└─$ zip2john common_pass_rules.zip > hashes.txt
ver 1.0 efh 5455 efh 7875 common_pass_rules.zip/flag.txt PKZIP Encr: 2b chk, TS_chk, cmplen=43, decmplen=31, crc=B68D4530 ts=AE5B cs=ae5b type=0

┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/hashed]
└─$ john hashes.txt --wordlist=/usr/share/wordlists/rockyou.txt
e/wordlists/rockyou.txt
john hashes.txt --wordlist=/usr/share/wordlists/rockyou.txt
Using default input encoding: UTF-8
Loaded 1 password hash (PKZIP [32/64])
Will run 2 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
0g 0:00:00:01 16.40% (ETA: 18:31:15) 0g/s 2493Kp/s 2493Kc/s 2493KC/s youssef2006..young77
01234567891234   (common_pass_rules.zip/flag.txt)
1g 0:00:00:05 DONE (2024-10-15 18:31) 0.1883g/s 2678Kp/s 2678Kc/s 2678KC/s 0124175354..0122782641
Use the "--show" option to display all of the cracked passwords reliably
Session completed.

┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/hashed]
└─$ john --show hashes.txt
common_pass_rules.zip/flag.txt:01234567891234:flag.txt:common_pass_rules.zip::common_pass_rules.zip

1 password hash cracked, 0 left

┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/hashed]
└─$ unzip -P 01234567891234 common_pass_rules.zip
Archive:  common_pass_rules.zip
 extracting: flag.txt

┌──(wil㉿DESKTOP-FKOIV4I)-[~/ctf/hashed]
└─$ cat flag.txt
flagmx{hashes_r_hard_to_crack}
```

## Notas adicionales
## Referencias