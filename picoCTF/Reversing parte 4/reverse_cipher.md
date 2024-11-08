## Objetivo
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev_this). Can you reverse the flag.

Hint
- objdump and Gihdra are some tools that could assist with this
## Solucion

``` python
rev = open('rev_this').read()
flag = ''

for i in range(8):
	flag += rev[i]

for j in range(8,24):
	if j&1 == 0:
		flag += chr(ord(rev[j]) - 5)
	else:
		flag += chr(ord(rev[j])+2)

flag += rev[23]
print(flag)
```

## Notas adicionales
## Referencias
