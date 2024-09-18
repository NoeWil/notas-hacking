## Objetivo
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/60786/` ([link](https://jupiter.challenges.picoctf.org/problem/60786/)) or http://jupiter.challenges.picoctf.org:60786

Hints.
- What is obfuscation?
## Solucion
Usamos jsnice para intentar desofuscar y obtenemos el siguiente arreglo.
```javascript
var _0x5a46 = ["f49bf}", "_again_e", "this", "Password Verified", "Incorrect password", "getElementById", "value", "substring", "picoCTF{", "not_this"];
```
Lo copiamos en la consola he intentamos armar la bandera
```javascript
cad [8] + cad [9] + cad[1] + cad [0]
'picoCTF{not_this_again_ef49bf}'
```
## Notas adicionales
## Referencias
- [Obfuscation (software) - Wikipedia](https://en.wikipedia.org/wiki/Obfuscation_(software))
- [JS NICE: Statistical renaming, Type inference and Deobfuscation](http://jsnice.org/)