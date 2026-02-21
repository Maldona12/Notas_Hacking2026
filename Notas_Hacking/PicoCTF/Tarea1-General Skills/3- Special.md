### special

### DESCRIPCIÓN

Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)Start your instance to see connection details.`ssh -p 58325 ctf-player@saturn.picoctf.net`
The password is `3f39b042`

### SOLUCIÓN

Al ingresar al servidor no se puede ingresar comandos como: ls, cat, dir por lo cual investigando me tope con el uso de las variables extenidas del Shell:

```
Special$ ${0}
${0} 
$ ls
blargh
$ cd blargh
$ cat blargh
cat: blargh: No such file or directory
$ cd blargh   
sh: 4: cd: can't cd to blargh
$ dir
flag.txt
$ flag.txt
sh: 6: flag.txt: not found
$ cat flag.txt   
picoCTF{5p311ch3ck_15_7h3_w0r57_f906e25a}
```

### NOTAS ADICIONALES

####  ¿Qué es `$0` en Bash?

- En sistemas Linux/Unix, `$0` es una **variable especial del shell** que contiene:
- El nombre del programa o shell que se está ejecutando actualmente.
#### ¿Qué hace `${0}`?
En bash:
- `$0` = valor de la variable
- `${0}` = exactamente lo mismo, pero usando sintaxis explícita de expansión

El entorno del reto implementa un mecanismo de autocorrección que modifica comandos ingresados por el usuario, impidiendo la ejecución directa de comandos como `bash`, `ls` o `cat`.

Sin embargo, el sistema no filtra expansiones de variables del shell.

Al ejecutar `${0}`, se invoca la variable especial `$0`, que contiene el nombre del shell actual. Esto provoca la ejecución de una nueva instancia del shell real sin pasar por el mecanismo de autocorrección, permitiendo así la ejecución normal de comandos y el acceso a la bandera.

### REFERENCIAS