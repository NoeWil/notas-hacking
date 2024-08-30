## Objetivo
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.
## Datos de acceso al nivel
* Username = bandit11
* password = dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
## Solucion
### Forma1
Usando cyberchef
### Forma 2
````bash
bandit11@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 Jul 17 15:57 .
drwxr-xr-x 70 root     root     4096 Jul 17 15:58 ..
-rw-r--r--  1 root     root      220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root     root     3771 Mar 31 08:41 .bashrc
-rw-r-----  1 bandit12 bandit11   49 Jul 17 15:57 data.txt
-rw-r--r--  1 root     root      807 Mar 31 08:41 .profile
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4
bandit11@bandit:~$ file data.txt
data.txt: ASCII text
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
bandit11@bandit:~$
````
### Forma 3
```python
bandit11@bandit:~$ python3
Python 3.12.3 (main, Apr 10 2024, 05:33:47) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import codecs
>>> codecs.decode("Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4", "ROT13")
'The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4'
>>>

```
## Notas adicionales
- ROT13 
## Referencias
[Rot13 on Wikipedia](https://en.wikipedia.org/wiki/ROT13)
