## Objetivo
Can you get the flag?Go to this [website](http://saturn.picoctf.net:60559/) and see what you can discover.

Hint
 - How is the password checked on this website? 
## Solucion
Ingresamos cualquier cosa después de que nos mandes en el mensaje que es incorrecto le damos a inspeccionar  y podremos ver la validación de la contraseña en el archivo secure.js

```javascript

function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```

Copiamos y obtenemos la bandera
```
picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb}
```
## Notas adicionales
## Referencias