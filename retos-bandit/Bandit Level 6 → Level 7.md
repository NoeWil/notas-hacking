## Objetivo

## Datos de acceso al nivel
* Username = bandit6
* password = HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
## Solucion
````bash
bandit6@bandit:~$ pwd
/home/bandit6
bandit6@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Jul 17 15:56 .
drwxr-xr-x 70 root root 4096 Jul 17 15:58 ..
-rw-r--r--  1 root root  220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root root 3771 Mar 31 08:41 .bashrc
-rw-r--r--  1 root root  807 Mar 31 08:41 .profile
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
bandit6@bandit:~$
````
## Notas adicionales
- 2>/dev/null permite formatear la salida eliminando los errores.
## Referencias