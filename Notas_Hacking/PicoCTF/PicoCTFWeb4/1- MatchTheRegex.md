### ### MatchTheRegex

### DESCRIPCIÓN

How about trying to match a regular expressionThe website is running [here](http://saturn.picoctf.net:53637/).
### SOLUCIÓN

En el código fuente de la pagina se nos proporcionó una expresión regular y debíamos construir una cadena que cumpliera exactamente con el patrón definido.

```
	function send_request() {
		let val = document.getElementById("name").value;
		// ^p.....F!?
		fetch(`/flag?input=${val}`)
			.then(res => res.text())
			.then(res => {
				const res_json = JSON.parse(res);
				alert(res_json.flag)
				return false;
			})
		return false;
	}
```

Analizando las restricciones como inicio y fin de la línea apoyándonos de la pagina regexr
construí una cadena que satisfacía todas las condiciones del patrón, lo que al introducir la candena
'p12345F'  era validada y nos arrojaba la bandera:

picoCTF{succ3ssfully_matchtheregex_08c310c6}
### NOTAS ADICIONALES

¿Qué es una expresión regular?

Una regex es un patrón que define reglas para validar texto.

### REFERENCIAS

https://regexr.com