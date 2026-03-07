### [Unminify](https://play.picoctf.org/practice/challenge/426)

### DESCRIPCIÓN

I don't like scrolling down to read the code of my website, so I've squished it. As a bonus, my pages load faster! Browse [here](http://titan.picoctf.net:61825/), and find the flag!
### SOLUCIÓN

- Abrir el sitio web del reto y presionar `Ctrl + U` para ver el **código fuente**.

- Al notar que el código está en una sola línea (minificado), copiar todo el contenido.

- Utilizar una herramienta como **js-beautifier** o el "Pretty Print".

- Al inspeccionar el código con formato, se observa que la bandera no está oculta por lógica compleja, sino que simplemente estaba "escondida" a simple vista por la falta de espacios.
  
- Buscar la cadena "picoCTF" dentro del código formateado. Se encuentra dentro de una clase o función de distribución del HTML.

picoCTF{pr3tty_c0d3_51d374f0}
### NOTAS ADICIONALES


### REFERENCIAS

https://beautifier.io/