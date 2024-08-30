## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data
## Datos de acceso al nivel
* Username = bandit10
* password = FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
## Solucion
### Forma 1
````bash
bandit10@bandit:~$ base64 -d data.txt
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
bandit10@bandit:~$
````
### Forma 2
Usando cyberchef
### Forma 3
Usando python

## Notas adicionales
**Base64** es un grupo de esquemas de codificación de binario a texto que transforma los datos binarios en una secuencia de caracteres imprimibles, limitada a un conjunto de 64 caracteres únicos.

## Referencias
- [Base64 on Wikipedia](https://en.wikipedia.org/wiki/Base64)
- [CyberChef ](https://gchq.github.io/CyberChef/)