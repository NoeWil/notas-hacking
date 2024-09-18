## Objetivo
Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/56830/` ([link](https://jupiter.challenges.picoctf.org/problem/56830/)) or http://jupiter.challenges.picoctf.org:56830

hints
What part of the website could tell you where the creator doesn't want you to look?
## Solucion
- Vamos a https://jupiter.challenges.picoctf.org/problem/56830/robots.txt
```
User-agent: *
Disallow: /1bb4c.html
```
Vamos a https://jupiter.challenges.picoctf.org/problem/56830/1bb4c.html
```
picoCTF{ca1cu1at1ng_Mach1n3s_1bb4c}
```
## Notas adicionales
## Referencias
- [Estándar de exclusión de robots - Wikipedia, la enciclopedia libre](https://es.wikipedia.org/wiki/Est%C3%A1ndar_de_exclusi%C3%B3n_de_robots)