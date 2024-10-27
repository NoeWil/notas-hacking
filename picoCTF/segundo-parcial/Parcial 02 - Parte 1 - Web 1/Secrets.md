## Objetivo
We have several pages hidden. Can you find the one with the flag?The website is running [here](http://saturn.picoctf.net:62644/).

Hint
- folders folders folders
## Solucion

Ingresamos a http://saturn.picoctf.net:62644/secret/hidden/superhidden/  y inspeccionamos

```html

<!DOCTYPE html>|
<html>|
	<head>|
	<title></title>|
	<link rel="stylesheet" href="[mycss.css (http://saturn.picoctf.net:62644/secret/hidden/superhidden/mycss.css)" />|
	</head>|

	<body>|
		<h1>Finally. You found me. But can you see me</h1>|
		<h3 class="flag">picoCTF{succ3ss_@h3n1c@10n_51b260fe}</h3>|
	</body>|
</html>|

```

## Notas adicionales
## Referencias