## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.
## Datos de acceso al nivel
* Username = bandit14
* password = MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
## Solucion
````bash
bandit14@bandit:~$ nc localhost 30000
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

^C
bandit14@bandit:~$
````
## Notas adicionales
- nc - es una herramient que permite conectarse a un host remoto, tambien podemos abrir un puerto
- nc localhost 30000
	- localhost - es el host o la maquina a la que me quiero conectar
	- 30000 - es el puerto que esta abierto o al
## Referencias
-  [How the Internet works in 5 minutes (YouTube)](https://www.youtube.com/watch?v=7_LPdttKXPc) (Not completely accurate, but good enough for beginners)
- [IP Addresses](https://computer.howstuffworks.com/web-server5.htm)
- [IP Address on Wikipedia](https://en.wikipedia.org/wiki/IP_address)
- [Localhost on Wikipedia](https://en.wikipedia.org/wiki/Localhost)
- [Ports](https://computer.howstuffworks.com/web-server8.htm)
- [Port (computer networking) on Wikipedia](https://en.wikipedia.org/wiki/Port_(computer_networking))
