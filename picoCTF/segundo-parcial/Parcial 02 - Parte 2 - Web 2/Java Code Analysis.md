## Objetivo
BookShelf Pico, my premium online book-reading service.I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://artifacts.picoctf.net/c/482/bookshelf-pico.zip).Website can be accessed [here!](http://saturn.picoctf.net:57029/).

Hints
- Maybe try to find the JWT Signing Key ("secret key") in the source code? Maybe it's hardcoded somewhere? Or maybe try to crack it?
- The 'role' and 'userId' fields in the JWT can be of interest to you!
- The 'role' and 'userId' fields in the JWT can be of interest to you!
- Upgrade your 'role' with the _new_ (cracked) JWT. And re-login for the new role to get reflected in browser's localStorage.

## Solucion
Mandar toket

```
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiQWRtaW4iLCJpc3MiOiJib29rc2hlbGYiLCJleHAiOjE3MzA1OTQ0MTMsImlhdCI6MTcyOTk4OTYxMywidXNlcklkIjoyLCJlbWFpbCI6IkFkbWluIn0.RDRxg9qNZ11sO1ISGPUBJe1G2xytp5cDF0o-pxUuCoE
```

## Notas adicionales
## Referencias