## Objetivo
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/129/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
Hint
- Do you know what `mod 37` means?
- `mod 37` means modulo 37. It gives the remainder of a number after being divided by 37.

## Solucion

```python
data = open('message.txt','r').read().split()

flag = 'picoCTF{'

for c in data:
	char = int(c) % 37
	if char >= 0 and char <= 25:
		s = chr(char + 65)
	elif char >= 26 and char <= 35:
		s = chr(char + 22)
	elif char == 36:
		s = '_'
	flag+= s

flag += '}'
print(flag)
```

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/crypto/basicmod1]
└─$ python3 mod1.py
picoCTF{R0UND_N_R0UND_ADD17EC2}
```
## Notas adicionales
## Referencias