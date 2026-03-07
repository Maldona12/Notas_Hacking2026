### [WebDecode](https://play.picoctf.org/practice/challenge/427)

### DESCRIPCIÓN

Do you know how to use the web inspector? Start searching [here](http://titan.picoctf.net:56137/) to find the flag
### SOLUCIÓN

- Abrir el sitio web del reto y navegar por las diferentes secciones de la página (Home, About, Contact).

- En la sección **About**, hacer clic derecho y seleccionar **Inspeccionar (Inspect)** para abrir las herramientas de desarrollador.

- Al revisar el código HTML, buscar una etiqueta `section` o `div` que contenga un atributo extraño.
 
- Se identifica un valor sospechoso en un atributo llamado `notify` , codificado en **Base64**:

- Copiar la cadena: `cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMWY4MzI2MTV9`
 
- En la terminal de **Kali Linux**, usar el siguiente comando para decodificarlo: 
```
┌──(kali㉿kali)-[~]
└─$ echo "cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMWY4MzI2MTV9" | base64 -d
```

picoCTF{web_succ3ssfully_d3c0ded_1f832615}
### NOTAS ADICIONALES


### REFERENCIAS