
### Glitch Cat

### DESCRIPCIÓN

Our flag printing service has started glitching!`$ nc saturn.picoctf.net 52873`
### SOLUCIÓN

  Al conectarse al servidor nos devuelve:
  
  'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'

Del cual podemos ver que esta de alguna manera codificado y se deben convertir esos números hexadecimales en chars 

Usando Python podemos convertirlas de una manera rápida y la forma que encontré fue esta:

```
>>> print(
...     "gl17ch_m3_n07_" +
...     chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) +
...     chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64)
... )
gl17ch_m3_n07_9c42a45d
>>>

```

picoCTF{gl17ch_m3_n07_9c42a45d}

### NOTAS ADICIONALES

Usar Python para decodificar  

### REFERENCIAS