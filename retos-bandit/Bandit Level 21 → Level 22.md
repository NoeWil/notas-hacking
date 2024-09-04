## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.
## Datos de acceso al nivel
* Username = bandit21
* password = EeoULMCra2q0dSkYj561DX7s1CpBuOBt
## Solucion
````bash
bandit21@bandit:~$ cat /etc/cron.d/cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
bandit21@bandit:~$
````
## Notas adicionales
- **Cron** -  en linux es una herramienta que permite programar y ejecutar tareas específicas dentro de nuestro sistema operativo Linux de forma automática. Esto, dentro de un periodo de tiempo determinado por el usuario
- /etc/cron.d - ahi ponemos los cronjobs, o dicho de otra forma, los archivos que quiero se ejecuten cada vez que arranca la computadora.
## Referencias
- [Cron]([Guía completa de Cron Job en Linux para principiantes en 5 pasos (donweb.com)](https://guias.donweb.com/guia-completa-de-cron-job-en-linux/#:~:text=Cron%20Job%20en%20linux%20es,tiempo%20determinado%20por%20el%20usuario.))
