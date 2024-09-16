## Objetivo
I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/137/challenge.zip)
## Solucion
``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.wCUqrF3ho1]
└─$ ls
challenge.zip  drop-in

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.wCUqrF3ho1]
└─$ cd drop-in/

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.wCUqrF3ho1/drop-in]
└─$ ls
message.txt

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.wCUqrF3ho1/drop-in]
└─$ cat message.txt
TOP SECRET

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.wCUqrF3ho1/drop-in]
└─$ git log
commit ef0b7cc6b98367fa168573c931e0f7098ef59182 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:20 2024 +0000

    remove sensitive info

commit ea859bf3b5d94ee74ce5ee1afa3edd7d4d6b35f0
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:20 2024 +0000

    create flag

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.wCUqrF3ho1/drop-in]
└─$ git checkout ea859bf3b5d94ee74ce5ee1afa3edd7d4d6b35f0
Note: switching to 'ea859bf3b5d94ee74ce5ee1afa3edd7d4d6b35f0'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at ea859bf create flag

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.wCUqrF3ho1/drop-in]
└─$ cat message.txt
picoCTF{s@n1t1z3_cf09a485}
```

## Notas adicionales

## Referencias
- [The CTF Primer (picoctf.org)](https://primer.picoctf.org/#_git_version_control)

