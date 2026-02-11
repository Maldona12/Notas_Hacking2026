### Wave a flag
  

### DESCRIPCIÓN

Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...[warm](https://challenge-files.picoctf.net/c_wily_courier/1e14db3a752e16eae2b0e0d73d9779f9c4ddfd8942f60f3285a2986068480316/warm)

### SOLUCIÓN

Usando las pistas, seguimos la serie de paso que nos menciona para poder descargar y ejecutar el programa, obteniendo la bandera 

```
  ┌──(kali㉿kali)-[~]
└─$ cd Desktop

┌──(kali㉿kali)-[~/Desktop]
└─$ chmod +x warm  

┌──(kali㉿kali)-[~/Desktop]
└─$ ./warm

Hello user! Pass me a -h to learn what I can do!

┌──(kali㉿kali)-[~/Desktop]
└─$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}

```

### NOTAS ADICIONALES

## *chmod* +x 

El comando `chmod +x` en sistemas Linux/Unix, incluyendo macOS, se utiliza para añadir permisos de ejecución (`x`) a un archivo o script, permitiendo que se ejecute directamente como un programa. Es comúnmente usado para convertir scripts, como los archivos `.sh` o `.py`, en ejecutables.

### REFERENCIAS