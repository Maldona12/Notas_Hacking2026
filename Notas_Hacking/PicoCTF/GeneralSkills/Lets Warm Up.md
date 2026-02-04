# 1-Lets Warm Up

  
DESCRIPCIÓN

If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?
  
SOLUCIÓN  

### Solucion 1 - Usando cyberchef

https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=MHg3MA  

p


picoctf(p)

### Solucion 2 - Usando Python
  
```

Python 3.12.0 (tags/v3.12.0:0fb18b0, Oct  2 2023, 13:03:39) [MSC v.1935 64 bit (AMD64)] on win32

Type "help", "copyright", "credits" or "license" for more information.

>>> int(0x70)

112

>>> chr(112)

'p'

>>>

```
NOTAS ADICIONALES

Cyberchef es una pagina que me permite decodificar en diferentes formatos
  
REFERENCIAS

https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=MHg3MA