### [Power Cookie](https://play.picoctf.org/practice/challenge/288)

### DESCRIPCIÓN


### SOLUCIÓN

- Acceder al sitio web del reto y presionar el botón **"Continue as guest"**.

- Una vez en la página, abrir la extensión **Cookie-Editor** 

- Localizar la cookie llamada `isAdmin`.

- Notar que su valor inicial es `0` (falso/invitado).    

- Cambiar el valor de `0` a `1` (verdadero/administrador) y guardar los cambios.

- Recargar la página (`F5`). El servidor ahora reconoce la sesión como administrador y muestra la bandera.
- 
picoCTF{gr4d3_A_c00k13_0d351e23}
### NOTAS ADICIONALES


### REFERENCIAS