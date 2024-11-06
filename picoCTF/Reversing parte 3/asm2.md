## Objetivo
What does asm2(0x4,0x21) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/7e3eb2f90200ac88126f62ceb4bc3948/test.S)

Hint
- assembly [conditions](https://www.tutorialspoint.com/assembly_programming/assembly_conditions.htm)
## Solucion

```python
>>> d = 33
>>> e = 4
>>> while e <= 64326:
...     d += 1
...     e += 116
...
>>> print(d)
588
>>> hex(d)
'0x24c'
>>>
```
## Notas adicionales
## Referencias