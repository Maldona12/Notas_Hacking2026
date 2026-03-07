### [IntroToBurp](https://play.picoctf.org/practice/challenge/419)

### DESCRIPCIÓN

Try [here](http://titan.picoctf.net:55469/) to find the flag
### SOLUCIÓN

Usando la herramienta Burp suite interceptamos la petición de verificación, a la cual para engañar al sistema y que nos permita entrar borramos el campo de OTP

- Abrir el enlace en el navegador integrado de Burp Suite (Proxy -> Open Browser).

- Completar el formulario de registro con datos aleatorios y presionar Register.

- En la pestaña de Intercept, activar Intercept is ON.

- En la página de "Two-Factor Authentication", introducir cualquier número y dar clic en Submit.

- En Burp Suite, localizar la petición POST y eliminar completamente la línea del parámetro otp:

- Antes: user=test&otp=1234

- Después: ( borrar otp=1234)

- Presionar Forward y desactivar el Intercept. La bandera aparecerá en la respuesta del navegador.

picoCTF{#0TP_Bypvss_SuCc3$S_9090d63c}
### NOTAS ADICIONALES


### REFERENCIAS