## Objetivo
Can you figure out how this program works to get the flag?Connect to the program with netcat:`$ nc saturn.picoctf.net 64339`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/528/picker-IV.c). The binary can be downloaded [here](https://artifacts.picoctf.net/c/528/picker-IV).

Hints
- With Python, there are no binaries. With compiled languages like C, there is source code, and there are binaries. Binaries are created from source code, they are a conversion from the human-readable source code, to the highly efficient machine language, in this case: x86_64.
- How can you find the address that `win` is at?

## Solucion

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-2/picker4]
└─$ readelf -s picker-IV

Symbol table '.dynsym' contains 15 entries:
   Num:    Value          Size Type    Bind   Vis      Ndx Name
     0: 0000000000000000     0 NOTYPE  LOCAL  DEFAULT  UND
     1: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND [...]@GLIBC_2.2.5 (2)
     2: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND puts@GLIBC_2.2.5 (2)
     3: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND [...]@GLIBC_2.2.5 (2)
     4: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND [...]@GLIBC_2.2.5 (2)
     5: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND fgetc@GLIBC_2.2.5 (2)
     6: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND [...]@GLIBC_2.2.5 (2)
     7: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND [...]@GLIBC_2.2.5 (2)
     8: 0000000000000000     0 NOTYPE  WEAK   DEFAULT  UND __gmon_start__
     9: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND [...]@GLIBC_2.2.5 (2)
    10: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND fopen@GLIBC_2.2.5 (2)
    11: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND __[...]@GLIBC_2.7 (3)
    12: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND exit@GLIBC_2.2.5 (2)
    13: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND sleep@GLIBC_2.2.5 (2)
    14: 0000000000404080     8 OBJECT  GLOBAL DEFAULT   26 [...]@GLIBC_2.2.5 (2)

Symbol table '.symtab' contains 76 entries:
   Num:    Value          Size Type    Bind   Vis      Ndx Name
     0: 0000000000000000     0 NOTYPE  LOCAL  DEFAULT  UND
     1: 0000000000400318     0 SECTION LOCAL  DEFAULT    1 .interp
     2: 0000000000400338     0 SECTION LOCAL  DEFAULT    2 .note.gnu.property
     3: 0000000000400358     0 SECTION LOCAL  DEFAULT    3 .note.gnu.build-id
     4: 000000000040037c     0 SECTION LOCAL  DEFAULT    4 .note.ABI-tag
     5: 00000000004003a0     0 SECTION LOCAL  DEFAULT    5 .gnu.hash
     6: 00000000004003c8     0 SECTION LOCAL  DEFAULT    6 .dynsym
     7: 0000000000400530     0 SECTION LOCAL  DEFAULT    7 .dynstr
     8: 00000000004005ca     0 SECTION LOCAL  DEFAULT    8 .gnu.version
     9: 00000000004005e8     0 SECTION LOCAL  DEFAULT    9 .gnu.version_r
    10: 0000000000400618     0 SECTION LOCAL  DEFAULT   10 .rela.dyn
    11: 0000000000400660     0 SECTION LOCAL  DEFAULT   11 .rela.plt
    12: 0000000000401000     0 SECTION LOCAL  DEFAULT   12 .init
    13: 0000000000401020     0 SECTION LOCAL  DEFAULT   13 .plt
    14: 00000000004010e0     0 SECTION LOCAL  DEFAULT   14 .plt.sec
    15: 0000000000401190     0 SECTION LOCAL  DEFAULT   15 .text
    16: 0000000000401448     0 SECTION LOCAL  DEFAULT   16 .fini
    17: 0000000000402000     0 SECTION LOCAL  DEFAULT   17 .rodata
    18: 000000000040209c     0 SECTION LOCAL  DEFAULT   18 .eh_frame_hdr
    19: 00000000004020f0     0 SECTION LOCAL  DEFAULT   19 .eh_frame
    20: 0000000000403e10     0 SECTION LOCAL  DEFAULT   20 .init_array
    21: 0000000000403e18     0 SECTION LOCAL  DEFAULT   21 .fini_array
    22: 0000000000403e20     0 SECTION LOCAL  DEFAULT   22 .dynamic
    23: 0000000000403ff0     0 SECTION LOCAL  DEFAULT   23 .got
    24: 0000000000404000     0 SECTION LOCAL  DEFAULT   24 .got.plt
    25: 0000000000404070     0 SECTION LOCAL  DEFAULT   25 .data
    26: 0000000000404080     0 SECTION LOCAL  DEFAULT   26 .bss
    27: 0000000000000000     0 SECTION LOCAL  DEFAULT   27 .comment
    28: 0000000000000000     0 FILE    LOCAL  DEFAULT  ABS crtstuff.c
    29: 00000000004011d0     0 FUNC    LOCAL  DEFAULT   15 deregister_tm_clones
    30: 0000000000401200     0 FUNC    LOCAL  DEFAULT   15 register_tm_clones
    31: 0000000000401240     0 FUNC    LOCAL  DEFAULT   15 __do_global_dtors_aux
    32: 0000000000404088     1 OBJECT  LOCAL  DEFAULT   26 completed.8061
    33: 0000000000403e18     0 OBJECT  LOCAL  DEFAULT   21 __do_global_dtor[...]
    34: 0000000000401270     0 FUNC    LOCAL  DEFAULT   15 frame_dummy
    35: 0000000000403e10     0 OBJECT  LOCAL  DEFAULT   20 __frame_dummy_in[...]
    36: 0000000000000000     0 FILE    LOCAL  DEFAULT  ABS picker-IV.c
    37: 0000000000000000     0 FILE    LOCAL  DEFAULT  ABS crtstuff.c
    38: 000000000040222c     0 OBJECT  LOCAL  DEFAULT   19 __FRAME_END__
    39: 0000000000000000     0 FILE    LOCAL  DEFAULT  ABS
    40: 0000000000403e18     0 NOTYPE  LOCAL  DEFAULT   20 __init_array_end
    41: 0000000000403e20     0 OBJECT  LOCAL  DEFAULT   22 _DYNAMIC
    42: 0000000000403e10     0 NOTYPE  LOCAL  DEFAULT   20 __init_array_start
    43: 000000000040209c     0 NOTYPE  LOCAL  DEFAULT   18 __GNU_EH_FRAME_HDR
    44: 0000000000404000     0 OBJECT  LOCAL  DEFAULT   24 _GLOBAL_OFFSET_TABLE_
    45: 0000000000401440     5 FUNC    GLOBAL DEFAULT   15 __libc_csu_fini
    46: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND putchar@@GLIBC_2.2.5
    47: 0000000000404080     8 OBJECT  GLOBAL DEFAULT   26 stdout@@GLIBC_2.2.5
    48: 0000000000404070     0 NOTYPE  WEAK   DEFAULT   25 data_start
    49: 0000000000401276    40 FUNC    GLOBAL DEFAULT   15 print_segf_message
    50: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND puts@@GLIBC_2.2.5
    51: 0000000000404080     0 NOTYPE  GLOBAL DEFAULT   25 _edata
    52: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND fclose@@GLIBC_2.2.5
    53: 0000000000401448     0 FUNC    GLOBAL HIDDEN    16 _fini
    54: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND printf@@GLIBC_2.2.5
    55: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND fgetc@@GLIBC_2.2.5
    56: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND __libc_start_mai[...]
    57: 0000000000404070     0 NOTYPE  GLOBAL DEFAULT   25 __data_start
    58: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND signal@@GLIBC_2.2.5
    59: 0000000000000000     0 NOTYPE  WEAK   DEFAULT  UND __gmon_start__
    60: 0000000000404078     0 OBJECT  GLOBAL HIDDEN    25 __dso_handle
    61: 0000000000402000     4 OBJECT  GLOBAL DEFAULT   17 _IO_stdin_used
    62: 00000000004013d0   101 FUNC    GLOBAL DEFAULT   15 __libc_csu_init
    63: 000000000040129e   150 FUNC    GLOBAL DEFAULT   15 win
    64: 0000000000404090     0 NOTYPE  GLOBAL DEFAULT   26 _end
    65: 00000000004011c0     5 FUNC    GLOBAL HIDDEN    15 _dl_relocate_sta[...]
    66: 0000000000401190    47 FUNC    GLOBAL DEFAULT   15 _start
    67: 0000000000404080     0 NOTYPE  GLOBAL DEFAULT   26 __bss_start
    68: 0000000000401334   144 FUNC    GLOBAL DEFAULT   15 main
    69: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND setvbuf@@GLIBC_2.2.5
    70: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND fopen@@GLIBC_2.2.5
    71: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND __isoc99_scanf@@[...]
    72: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND exit@@GLIBC_2.2.5
    73: 0000000000404080     0 OBJECT  GLOBAL HIDDEN    25 __TMC_END__
    74: 0000000000000000     0 FUNC    GLOBAL DEFAULT  UND sleep@@GLIBC_2.2.5
    75: 0000000000401000     0 FUNC    GLOBAL HIDDEN    12 _init

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-2/picker4]
└─$ readelf -s picker-IV | grep win
    63: 000000000040129e   150 FUNC    GLOBAL DEFAULT   15 win

┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-2/picker4]
└─$ nc saturn.picoctf.net 64339
Enter the address in hex to jump to, excluding '0x': 000000000040129e
You input 0x40129e
You won!
picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_14bc5444}
```

## Solucion 2

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/reversing/parte-2/picker4]
└─$ gdb picker-IV
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
Reading symbols from picker-IV...
(No debugging symbols found in picker-IV)
(gdb) info function
All defined functions:

Non-debugging symbols:
0x0000000000401000  _init
0x00000000004010e0  putchar@plt
0x00000000004010f0  puts@plt
0x0000000000401100  fclose@plt
0x0000000000401110  printf@plt
0x0000000000401120  fgetc@plt
0x0000000000401130  signal@plt
0x0000000000401140  setvbuf@plt
0x0000000000401150  fopen@plt
0x0000000000401160  __isoc99_scanf@plt
0x0000000000401170  exit@plt
0x0000000000401180  sleep@plt
0x0000000000401190  _start
0x00000000004011c0  _dl_relocate_static_pie
0x00000000004011d0  deregister_tm_clones
0x0000000000401200  register_tm_clones
0x0000000000401240  __do_global_dtors_aux
0x0000000000401270  frame_dummy
0x0000000000401276  print_segf_message
0x000000000040129e  win
0x0000000000401334  main
0x00000000004013d0  __libc_csu_init
0x0000000000401440  __libc_csu_fini
0x0000000000401448  _fini
(gdb)
```
## Notas adicionales
## Referencias