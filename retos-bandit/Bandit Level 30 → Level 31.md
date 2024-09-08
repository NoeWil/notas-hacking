## Objetivo

## Datos de acceso al nivel

* Username = bandit30
* password = qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
## Solucion
````bash
bandit30@bandit:~$ mktemp -d
/tmp/tmp.6rThcuPVHC
bandit30@bandit:~$ cd /tmp/tmp.6rThcuPVHC
bandit30@bandit:/tmp/tmp.6rThcuPVHC$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit30/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit30/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit30-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
bandit30@bandit:/tmp/tmp.6rThcuPVHC$ cd repo/
bandit30@bandit:/tmp/tmp.6rThcuPVHC/repo$ ls
README.md
bandit30@bandit:/tmp/tmp.6rThcuPVHC/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/tmp.6rThcuPVHC/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
bandit30@bandit:/tmp/tmp.6rThcuPVHC/repo$ git tag
secret
bandit30@bandit:/tmp/tmp.6rThcuPVHC/repo$ git show secret
fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
bandit30@bandit:/tmp/tmp.6rThcuPVHC/repo$
````
## Notas adicionales
- **`git tag`**: Muestra una lista de todas las etiquetas en el repositorio. Si no se proporciona ninguna opción adicional, solo muestra los nombres de las etiquetas.
- `git show` : Se utiliza para mostrar detalles sobre un objeto específico en el repositorio, como un commit, una etiqueta, un árbol o un blob.
## Referencias