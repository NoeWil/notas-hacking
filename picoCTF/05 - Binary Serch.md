## Objetivo
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/19/challenge.zip)

Additional details will be available after launching your challenge instance.
## Solucion
``` bash
┌──(wil㉿DESKTOP-FKOIV4I)-[/tmp/tmp.xgyTRoUq7P]
└─$ ssh -p 51218 ctf-player@atlas.picoctf.net
The authenticity of host '[atlas.picoctf.net]:51218 ([18.217.83.136]:51218)' can't be established.
ED25519 key fingerprint is SHA256:M8hXanE8l/Yzfs8iuxNsuFL4vCzCKEIlM/3hpO13tfQ.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? y
Please type 'yes', 'no' or the fingerprint: yes
Warning: Permanently added '[atlas.picoctf.net]:51218' (ED25519) to the list of known hosts.
ctf-player@atlas.picoctf.net's password:
Permission denied, please try again.
ctf-player@atlas.picoctf.net's password:
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Lower! Try again.
Enter your guess: 300
Higher! Try again.
Enter your guess: 400
Lower! Try again.
Enter your guess: 350
Higher! Try again.
Enter your guess: 380
Lower! Try again.
Enter your guess: 375
Lower! Try again.
Enter your guess: 370
Higher! Try again.
Enter your guess: 373
Lower! Try again.
Enter your guess: 372
Lower! Try again.
Enter your guess: 371
Congratulations! You guessed the correct number: 371
Here's your flag: picoCTF{g00d_gu355_1597707f}
Connection to atlas.picoctf.net closed.
```
## Notas adicionales
## Referencias