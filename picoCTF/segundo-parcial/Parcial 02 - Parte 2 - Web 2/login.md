## Objetivo
My dog-sitter's brother made this website but I can't get in; can you help?[login.mars.picoctf.net](https://login.mars.picoctf.net/)

## Solucion

intentamos ingresar despues inspeccionamos y obtenemos lo siguiente

```JavaScript
(async () => {
    await new Promise((e => window.addEventListener("load", e))),
    document.querySelector("form").addEventListener("submit", (e => {
        e.preventDefault();
        const r = {
            u: "input[name=username]",
            p: "input[name=password]"
        }
          , t = {};
        for (const e in r)
            t[e] = btoa(document.querySelector(r[e]).value).replace(/=/g, "");
        return "YWRtaW4" !== t.u ? alert("Incorrect Username") : "cGljb0NURns1M3J2M3JfNTNydjNyXzUzcnYzcl81M3J2M3JfNTNydjNyfQ" !== t.p ? alert("Incorrect Password") : void alert(`Correct Password! Your flag is ${atob(t.p)}.`)
    }
    ))
}
)();

```

Usamos un decodificador de base 64 y obtenemos la bandera.

```
picoCTF{53rv3r_53rv3r_53rv3r_53rv3r_53rv3r}
```
## Notas adicionales
## Referencias
- [Base64 Decode and Encode - Online](https://www.base64decode.org/)