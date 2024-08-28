## Objetivo

## Datos de acceso al nivel
* Username = bandit5
* password = 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
## Solucion
````bash
bandit5@bandit:~$ cd inhere/
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15  maybehere18
maybehere01  maybehere04  maybehere07  maybehere10  maybehere13  maybehere16  maybehere19
maybehere02  maybehere05  maybehere08  maybehere11  maybehere14  maybehere17
bandit5@bandit:~/inhere$ find . -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
bandit5@bandit:~/inhere$
````
## Notas adicionales
- ls -R esta opción permite listar archivos de forma recursiva, es decir, las carpetas con las subcarpetas.
- El comando `find` permite buscar archivos según varios criterios:
	- `-readable`: archivos que sean legibles.
	- `-size`: el tamaño del archivo (por ejemplo, `c` para bytes).
	- `-type`: el tipo de archivo (por ejemplo, `f` para archivos regulares no ejecutables).-
## Referencias