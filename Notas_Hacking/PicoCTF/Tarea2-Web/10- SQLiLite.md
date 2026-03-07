### [SQLiLite](https://play.picoctf.org/practice/challenge/304)

### DESCRIPCIÓN

Can you login to this website?
### SOLUCIÓN

- El reto presenta un formulario de login vulnerable a inyección SQL.
 
- El objetivo es omitir la verificación de la contraseña manipulando la consulta (query) que el servidor envía a la base de datos.
 
- En el campo de **Username**, ingresar `admin`.
 
- En el campo de **Password**, ingresar una cadena que rompa la lógica booleana: `' or '1'='1`.

- Al enviar el formulario, la consulta resultante en el servidor se convierte en algo similar a: `SELECT * FROM users WHERE username='admin' AND password='' or '1'='1'`

- Como `'1'='1'` siempre es cierto, el servidor autoriza el acceso.
 
- Al iniciar sesión, la bandera estará en el código fuente de la pagina

picoCTF{L00k5_l1k3_y0u_solv3d_it_d3c660ac}
### NOTAS ADICIONALES


### REFERENCIAS