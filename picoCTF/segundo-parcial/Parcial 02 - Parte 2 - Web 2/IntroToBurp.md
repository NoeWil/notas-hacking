## Objetivo
Try [here](http://titan.picoctf.net:54368/) to find the flag

Hint
- Try using burpsuite to intercept request to capture the flag.
- Try mangling the request, maybe their server-side code doesn't handle malformed requests very well.
## Solucion

Capturamos el trafico y cuando se captura el que contiene la linea opt al final la borramos y damos forward

```
Welcome, a you sucessfully bypassed the OTP request. Your Flag: picoCTF{#0TP_Bypvss_SuCc3$S_2e80f1fd}
```

## Notas adicionales
## Referencias