## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

## Solucion

``` python
from scapy.all import *

packets = rdpcap('capture.pcap')

flag=''

for p in packets:
	if UDP in p and p[UDP].dport ==22:
		if p[UDP].sport > 5000:
			flag+= chr(p[UDP].sport-5000)

print(flag)
```

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/sharkonwire2]
└─$ python3 exp.py
picoCTF{p1LLf3r3d_data_v1a_st3g0}

┌──(wil㉿DESKTOP-FKOIV4I)-[~/forensic/sharkonwire2]
└─$
```
## Notas adicionales
## Referencias