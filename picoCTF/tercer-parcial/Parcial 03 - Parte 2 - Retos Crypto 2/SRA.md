## Objetivo
I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...Connect to the program on our server: `nc saturn.picoctf.net 60445`Download the program: [chal.py](https://artifacts.picoctf.net/c/293/chal.py)

## Solucion

``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~/picoCTF/tercer-parcial/crypto2/RSA]
└─$ python3 solve.py
[+] Opening connection to saturn.picoctf.net on port 60445: Done
/home/wil/picoCTF/tercer-parcial/crypto2/RSA/solve.py:19: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("anger =")
/home/wil/picoCTF/tercer-parcial/crypto2/RSA/solve.py:21: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("envy =")
cipher= 23483637855962173460513844118713982505389811999669635223945659718919719670878
d= 34861144682097783716835062706244651178482362920262601611425820260517778804505
/home/wil/picoCTF/tercer-parcial/crypto2/RSA/solve.py:25: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("vainglory?"))
b'vainglory?'
Give me the divisors of  2284694839030642451450219504579155704284198618705250121808013982413553669510844184
[2, 2, 2, 3, 7, 17, 179, 193, 373, 3119, 4691, 39161, 6936569, 56542019, 3666499267, 2602016261629067, 28956003003133033519]
{172070835230684279980486693666463366309, 288127539740607102999665318470381571177, 221679725869833295487583994750635342847, 224371638202413974737729271747554406807, 265153770812349643306179224519386660793, 291094817757384662173059123397061632877, 186099128124941163824449126449804265417, 246931633893708562448915694315915176807, 281419292258751657763010065030428469657}
f9VUN75dLLwupXeW
/home/wil/picoCTF/tercer-parcial/crypto2/RSA/solve.py:46: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.sendline(plaintext.decode())
b'> f9VUN75dLLwupXeW\r\n'
b'Conquered!\r\n'
b'picoCTF{7h053_51n5_4r3_n0_m0r3_0795e891}\r\n'
f9VUN75dLLwupXeW
[*] Closed connection to saturn.picoctf.net port 60445
```

```python
from pwn import *
import primefac
from itertools import combinations
from Crypto.Util.number import long_to_bytes

def sub_lists (l):
    comb = []

    #Iterating till length of list
    for i in range(1,len(l)+1):
        comb += [list(j) for j in combinations(l, i)]
    return comb

def divisors(phi):
   print("Give me the divisors of ", phi-1)
   return(eval(input()))

r = remote('saturn.picoctf.net', 60445)
r.recvuntil("anger =")
ciphertext=int(r.recvline())
r.recvuntil("envy =")
d=int(r.recvline())
print("cipher=",ciphertext)
print("d=",d)
print(r.recvuntil("vainglory?"))
r.recvline()
factors=divisors(d*65537)
combos = sub_lists(factors)
primes = set()

for l in combos:
   product = 1
   for k in l:
      product = product * k
   if product.bit_length()==128 and primefac.isprime(product+1):
      primes.add(product+1)
print(primes)
primelist = list(primes)
for p in primelist:
   for q in primelist:
      n=p*q
      plain = pow(ciphertext,d,n)
      try:
         plaintext = long_to_bytes(plain)
         print(plaintext.decode())
         r.sendline(plaintext.decode())
         print(r.recvline())
         print(r.recvline())
         print(r.recvline())
      except:
         continue
```
## Notas adicionales
## Referencias