## Objetivo

## Datos de acceso al nivel
* Username = bandit19
* password = cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
## Solucion
````bash
bandit19@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Jul 17 15:57 .
drwxr-xr-x 70 root     root      4096 Jul 17 15:58 ..
-rwsr-x---  1 bandit20 bandit19 14880 Jul 17 15:57 bandit20-do
-rw-r--r--  1 root     root       220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root     root      3771 Mar 31 08:41 .bashrc
-rw-r--r--  1 root     root       807 Mar 31 08:41 .profile
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
bandit19@bandit:~$
````
## Notas adicionales
- setuid - es un bit que se puede modificar en un ejecutable para darle permisos a un usuario especifico
## Referencias
- [setuid on Wikipedia](https://en.wikipedia.org/wiki/Setuid)
- 