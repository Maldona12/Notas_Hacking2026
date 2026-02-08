
### First Grep
  
### DESCRIPCIÓN

Can you find the flag in the file? This would be really tedious to look through manually, something tells me there is a better way.The flag is in this [file](https://challenge-files.picoctf.net/c_fickle_tempest/92807684f3e52665caaf90d69e1e661f990b8731b2f8005e18631be23ff991bb/file).

### SOLUCIÓN

### Solución 1 - Usando una función de búsqueda en un editor de texto 

Usando ctrl + b en el editor de texto se busco la palabra "pico"

picoCTF{grep_is_good_to_find_things_eb80073D}

### Solución 2 - Usando Grep en Python

```
import re

def grep(ruta_archivo):

    with open(ruta_archivo, 'r') as archivo:

        contenido = archivo.read()

        # Buscar picoCTF{...}

        resultados = re.findall(r'picoCTF\{[^}]+\}', contenido)

        for flag in resultados:

            print(f"Flag encontrada: {flag}")

grep("file.txt")
```

Flag encontrada: picoCTF{grep_is_good_to_find_things_eb80073D}
### NOTAS ADICIONALES

  Al parecer en Linux la funcion Grep es mas sencilla y se usa de esta manera:
  
```

strings file.txt | grep -i pico
# o
grep -r "picoCTF{" file.txt

```

Al probarlo en una maquina virtual con Kali Linux instalado aparece el texto "picoCTF{"  marcado como en rojo 

### REFERENCIAS

[^1]: 
