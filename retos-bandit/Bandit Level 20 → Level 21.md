## Objetivo
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think
## Datos de acceso al nivel
* Username = bandit20
* password = 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
## Solucion
````bash

bandit20@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Jul 17 15:57 .
drwxr-xr-x 70 root     root      4096 Jul 17 15:58 ..
-rw-r--r--  1 root     root       220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root     root      3771 Mar 31 08:41 .bashrc
-rw-r--r--  1 root     root       807 Mar 31 08:41 .profile
-rwsr-x---  1 bandit21 bandit20 15604 Jul 17 15:57 suconnect
bandit20@bandit:~$ nc -lnvp 2024 <<< 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO &
[1] 3136511
bandit20@bandit:~$ Listening on 0.0.0.0 2024

bandit20@bandit:~$ ./suconnect 2024
Connection received on 127.0.0.1 36626
Read: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
Password matches, sending next password
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
[1]+  Done                    nc -lnvp 2024 <<< 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
bandit20@bandit:~$
````
## Notas adicionales
- nc - Se utliza para abrir puertos.
- & - sis agregamos un simbolo de estos al final de un comando, lo estamos enviado al segundo plano.
- jobs - me muestras los procesos que se encuentras en segundo plano.
- fg - saca un proceso o comando de segundo plano y lo trae al primer plano.
## Referencias