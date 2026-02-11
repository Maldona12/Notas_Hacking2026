### Bases

DESCRIPCIÓN

What does this bDNhcm5fdGgzX3IwcDM1 mean? I think it has something to do with bases.  

SOLUCIÓN

### Solución 1 - Usando Cyberchef

bDNhcm5fdGgzX3IwcDM1

l3arn_th3_r0p35

picoCTF{l3arn_th3_r0p35}


### Solución 2 - Usando Python

```
Python 3.12.0 (tags/v3.12.0:0fb18b0, Oct  2 2023, 13:03:39) [MSC v.1935 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> import base64
>>> s = "bDNhcm5fdGgzX3IwcDM1"
>>> print(base64.b64decode(s).decode())
l3arn_th3_r0p35
>>>
```

picoCTF{l3arn_th3_r0p35}


### Solución 3 - Usando la Consola

echo 'bDNhcm5fdGgzX3IwcDM1' | base64 -d


NOTAS ADICIONALES

Gracias a la pista que viene en el reto puedes deducir que tienes que convertir o decodificar en base64, investigando encontré una forma de hacerlo con Python
  

REFERENCIAS

https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=YkROaGNtNWZkR2d6WDNJd2NETTE&oeol=FF

https://www.geeksforgeeks.org/python/encoding-and-decoding-base64-strings-in-python/