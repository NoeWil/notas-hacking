## Objetivo
Now for something a little different. `0x2262c96b` is loaded into memory in the `main` function. Examine byte-wise the memory that the constant is loaded in by using the GDB command `x/4xb addr`. The flag is the four bytes as they are stored in memory. If you find the bytes `0x11 0x22 0x33 0x44` in the memory location, your flag would be: `picoCTF{0x11223344}`.Debug [this](https://artifacts.picoctf.net/c/531/debugger0_c).

Hint
- You'll need to breakpoint the instruction after the memory load.
- Use the gdb command `x/4xb addr` with the memory location as the address `addr` to examine. [GDB manual page](https://ftp.gnu.org/old-gnu/Manuals/gdb/html_node/gdb_55.html).
- Any registers in `addr` should be prepended with `$` like `$rbp`.
- Don't use square brackets for `addr`
- What is [endianness](https://en.wikipedia.org/wiki/Endianness)?
## Solucion

```bash
└─$ gdb ./debugger0_b
GNU gdb (Debian 13.2-1+b2) 13.2
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from ./debugger0_b...
(No debugging symbols found in ./debugger0_b)
(gdb) set disassembly-flavor intel
(gdb) info f
files         float         frame         frame-filter  functions
(gdb) info functions
All defined functions:

Non-debugging symbols:
0x0000000000401000  _init
0x0000000000401020  _start
0x0000000000401050  _dl_relocate_static_pie
0x0000000000401060  deregister_tm_clones
0x0000000000401090  register_tm_clones
0x00000000004010d0  __do_global_dtors_aux
0x0000000000401100  frame_dummy
0x0000000000401106  main
0x0000000000401150  __libc_csu_init
0x00000000004011c0  __libc_csu_fini
0x00000000004011c8  _fini
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:     endbr64
   0x000000000040110a <+4>:     push   rbp
   0x000000000040110b <+5>:     mov    rbp,rsp
   0x000000000040110e <+8>:     mov    DWORD PTR [rbp-0x14],edi
   0x0000000000401111 <+11>:    mov    QWORD PTR [rbp-0x20],rsi
   0x0000000000401115 <+15>:    mov    DWORD PTR [rbp-0x4],0x1e0da
   0x000000000040111c <+22>:    mov    DWORD PTR [rbp-0xc],0x25f
   0x0000000000401123 <+29>:    mov    DWORD PTR [rbp-0x8],0x0
   0x000000000040112a <+36>:    jmp    0x401136 <main+48>
   0x000000000040112c <+38>:    mov    eax,DWORD PTR [rbp-0x8]
   0x000000000040112f <+41>:    add    DWORD PTR [rbp-0x4],eax
   0x0000000000401132 <+44>:    add    DWORD PTR [rbp-0x8],0x1
   0x0000000000401136 <+48>:    mov    eax,DWORD PTR [rbp-0x8]
   0x0000000000401139 <+51>:    cmp    eax,DWORD PTR [rbp-0xc]
   0x000000000040113c <+54>:    jl     0x40112c <main+38>
   0x000000000040113e <+56>:    mov    eax,DWORD PTR [rbp-0x4]
   0x0000000000401141 <+59>:    pop    rbp
   0x0000000000401142 <+60>:    ret
End of assembler dump.
(gdb) break main
Breakpoint 1 at 0x40110e
(gdb) layout asm

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2/gdb-baby-2]
└─$

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2/gdb-baby-2]
└─$
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2/gdb-baby-2]
└─$ cd ..

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2]
└─$ mkdir gdb-baby-3

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2]
└─$ cd gdb-baby-3

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2/gdb-baby-3]
└─$ wget https://artifacts.picoctf.net/c/531/debugger0_c
--2024-11-22 21:45:19--  https://artifacts.picoctf.net/c/531/debugger0_c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.144.104, 18.154.144.85, 18.154.144.107, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.144.104|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16304 (16K) [application/octet-stream]
Saving to: ‘debugger0_c’

debugger0_c                   100%[=================================================>]  15.92K  --.-KB/s    in 0.001s

2024-11-22 21:45:20 (12.1 MB/s) - ‘debugger0_c’ saved [16304/16304]


┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2/gdb-baby-3]
└─$ chmod +x debugger0_c

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/reversing-2/gdb-baby-3]
└─$ gdb debugger0_c
GNU gdb (Debian 13.2-1+b2) 13.2
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from debugger0_c...
(No debugging symbols found in debugger0_c)
(gdb) set disassembly-flavor intel
(gdb) info functions
All defined functions:

Non-debugging symbols:
0x0000000000401000  _init
0x0000000000401020  _start
0x0000000000401050  _dl_relocate_static_pie
0x0000000000401060  deregister_tm_clones
0x0000000000401090  register_tm_clones
0x00000000004010d0  __do_global_dtors_aux
0x0000000000401100  frame_dummy
0x0000000000401106  main
0x0000000000401130  __libc_csu_init
0x00000000004011a0  __libc_csu_fini
0x00000000004011a8  _fini
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:     endbr64
   0x000000000040110a <+4>:     push   rbp
   0x000000000040110b <+5>:     mov    rbp,rsp
   0x000000000040110e <+8>:     mov    DWORD PTR [rbp-0x14],edi
   0x0000000000401111 <+11>:    mov    QWORD PTR [rbp-0x20],rsi
   0x0000000000401115 <+15>:    mov    DWORD PTR [rbp-0x4],0x2262c96b
   0x000000000040111c <+22>:    mov    eax,DWORD PTR [rbp-0x4]
   0x000000000040111f <+25>:    pop    rbp
   0x0000000000401120 <+26>:    ret
End of assembler dump.
(gdb) break main
Breakpoint 1 at 0x40110e
(gdb) run
Starting program: /home/wil/picoCTF/tercer-parcial/reversing-2/gdb-baby-3/debugger0_c
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000000000040110e in main ()
(gdb) break *0x40111f
Breakpoint 2 at 0x40111f
(gdb) c
Continuing.

Breakpoint 2, 0x000000000040111f in main ()
(gdb) info registers eax
eax            0x2262c96b          576899435
(gdb) x/4xb $rbp-4
0x7fffffffddbc: 0x6b    0xc9    0x62    0x22
(gdb) exit
A debugging session is active.

        Inferior 1 [process 1490] will be killed.

Quit anyway? (y or n) y
```

## Notas adicionales
## Referencias