kali
### [Local Authority](https://play.picoctf.org/practice/challenge/278)

### DESCRIPCIÓN

Can you get the flag? Go to this [website](http://saturn.picoctf.net:60027/) and see what you can discover.
### SOLUCIÓN

-  Entrar a la web del reto e intentar un login fallido (ej. `admin` : `admin`). Esto nos redirige a una página de error de login.

- . Revisar el código fuente de la página de error (`login.php`) y notar que utiliza un script externo: `<script src="secure.js"></script>`.

-  Acceder directamente al archivo JS.

- Al revisar el contenido del archivo, se encuentran las credenciales en texto plano dentro de la función de validación:


```
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```

- Regresar a la página principal de login e ingresar con el usuario **admin** y la contraseña **strongPassword098765**.

- El sistema redirigirá al panel de administración donde se muestra la bandera.
 

**Flag:** `picoCTF{n0_m0r3_l0c4l_4u7h_b71e1957}`
### NOTAS ADICIONALES


### REFERENCIAS