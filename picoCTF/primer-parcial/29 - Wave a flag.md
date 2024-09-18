## Objetivo
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm) has extraordinarily helpful information...
## Solucion
``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.g0ZHIeDEng]
└─$ chmod +x warm

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.g0ZHIeDEng]
└─$ ./warm
Hello user! Pass me a -h to learn what I can do!

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.g0ZHIeDEng]
└─$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_30e77291}

┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.g0ZHIeDEng]
└─$

```
## Notas adicionales
## Referencias