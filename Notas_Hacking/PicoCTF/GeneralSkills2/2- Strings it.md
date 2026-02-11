### strings it

### DESCRIPCIÓN

Can you find the flag in [file](https://challenge-files.picoctf.net/c_fickle_tempest/285538e2710605958a055500d6573657fcafea6308545cecfabb34462199cfd5/strings) without running it?
### SOLUCIÓN

Investigando que hace el comando Strings, lo use para ver el archivo dando como resultado una gran cantidad de texto por lo cual utilizando lo que aprendí en los ejercicios anteriores use ' | ' y el comando grep para encontrar la bandera:

```
┌──(kali㉿kali)-[~/Desktop]
└─$ strings strings | grep pico
picoCTF{5tRIng5_1T_1067EC4c}

```

### NOTAS ADICIONALES

## *Strings*

El comando `strings` en Linux ==extrae secuencias de caracteres imprimibles (texto legible) de archivos no textuales o binarios==, como ejecutables, bibliotecas y archivos objeto. Por defecto, busca cadenas de 4 o más caracteres terminadas en nulo o salto de línea, facilitando la depuración, auditoría de seguridad y forense digital.

### REFERENCIAS