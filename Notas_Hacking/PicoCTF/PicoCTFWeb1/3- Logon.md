### logon

### DESCRIPCIÓN

The factory is hiding things from all of its users.Can you login as Joe and find what they've been looking at? http://fickle-tempest.picoctf.net:59227
### SOLUCIÓN

Usando un modificador de cookies que funcione en tu navegador, nos registramos con cualquier usuario y cambiamos el False del admin por True 

picoCTF{th3_c0nsp1r4cy_l1v3s_4d184b0d}

 Se puede obtener la bandera modificando la cookie desde la consola, de la siguiente manera:

curl -s [http://fickle-tempest.picoctf.net:59227/flag](http://fickle-tempest.picoctf.net:59227/flag) -H "Cookie: password=carlos; username=carlos; admin=True" | grep pico


### NOTAS ADICIONALES

- Ver como funcionan las peticiones y las respuestas de los servidores 

### REFERENCIAS