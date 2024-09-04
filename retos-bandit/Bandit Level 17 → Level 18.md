## Objetivo
There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**
## Datos de acceso al nivel
* Username = bandit17
* password = EReVavePLFHtFlFsjn3hyzMlvSuSAcRD
## Solucion
````bash
bandit17@bandit:~$ diff passwords.old passwords.new
42c42
< bSrACvJvvBSxEM2SGsV5sn09vc3xgqyp
---
> x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
bandit17@bandit:~$
````
## Notas adicionales
- diff - es un comando con el cual puedes comparar dos archivos de textos con el cual se puede mostrar sus diferencias.
## Referencias