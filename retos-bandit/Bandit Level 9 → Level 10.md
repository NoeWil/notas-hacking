## Objetivo

## Datos de acceso al nivel
* Username = bandit9
* password = 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
## Solucion
````bash
bandit9@bandit:~$ strings data.txt | grep ==
\a!;========== the
========== passwordf
========== isc
========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
bandit9@bandit:~$
````
## Notas adicionales
el comando `strings data.txt | grep ==` extrae todas las secuencias de texto imprimibles del archivo `data.txt` y luego filtra esas secuencias para mostrar solo las que contienen `==`
## Referencias