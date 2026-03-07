### [Secrets](https://play.picoctf.org/practice/challenge/296)

### DESCRIPCIÓN

We have several pages hidden. Can you find the one with the flag? The website is running [here](http://saturn.picoctf.net:59137/).
### SOLUCIÓN

- nspeccionar el código fuente (`Ctrl + U`) de la página de inicio. Se identifica una ruta hacia archivos dentro de una carpeta llamada `secret/` (ej: `secret/assets/index.css`).

- Navegar manualmente a la URL: `http://[URL-RETO]/secret/`.
  
- En la página de "secret", volver a inspeccionar el código fuente. Se encuentra una referencia a una subcarpeta llamada `hidden/`.    

- Navegar a: `http://[URL-RETO]/secret/hidden/`.

- En la página de "hidden", inspeccionar el código una vez más. Se localiza una tercera carpeta llamada `superhidden/`.    

- Navegar a la ruta final: `http://[URL-RETO]/secret/hidden/superhidden/`.

- Al cargar la página en `/superhidden/`, revisar el código fuente (`view-source`). La bandera se encuentra en el cuerpo del HTML.
### NOTAS ADICIONALES


### REFERENCIAS