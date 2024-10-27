## Objetivo
Download the packet capture file and use packet analysis software to find the flag.

- [Download packet capture](https://artifacts.picoctf.net/c/194/network-dump.flag.pcap)
Hint
- Wireshark, if you can install and use it, is probably the most beginner friendly packet analysis software product.
## Solucion

```bash
strings network-dump.flag.pcap | grep "p i c o"| tr -d ' '
picoCTF{p4ck37_5h4rk_ceccaa7f}
```

## Notas adicionales
## Referencias