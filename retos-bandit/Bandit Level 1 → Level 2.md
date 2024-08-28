## Objetivo
The password for the next level is stored in a file called **-** located in the home directory
## Datos de acceso al nivel
* Username = bandit1
* password = ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
## Solucion
````text
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat -
^C
bandit1@bandit:~$ cat ./-
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
bandit1@bandit:~$
````
## Notas adicionales
Si le paso un - al cat pensara que le quiero pasar un parametro y se confunde
Si en nombre del archivo inicia con -, hay que anteponer al nombre ./ o poner la ruta completa del archivo.
## Referencias
- [Google Search for “dashed filename”](https://www.google.com/search?q=dashed+filename)
- [Advanced Bash-scripting Guide - Chapter 3 - Special Characters](https://linux.die.net/abs-guide/special-chars.html)