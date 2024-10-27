## Objetivo
Can you find the flag? [shark2.pcapng](https://mercury.picoctf.net/static/719e81d6fbb6b3157624268588fc0de8/shark2.pcapng).

Hint
- Did you really find _the_ flag?
- Look for traffic that seems suspicious.
## Solucion

Uso de wireshark, en la barra de filtros ponemos dns and ip.dst= =18.217.1.57 copiamos los encabezados de la info y lo decodeabos en base 64 y obtenemos la bandera.

```
picoCTF{dns_3xf1l_ftw_deadbeef}
```

## Notas adicionales
## Referencias