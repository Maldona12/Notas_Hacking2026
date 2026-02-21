### blame game

### DESCRIPCIÓN

Someone's commits seems to be preventing the program from working. Who is it?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/73/challenge.zip)

### SOLUCIÓN

Descargamos el archivo con wget
Descomprimimos con unzip
Entramos a la carpeta usando Cd
Usamos comandos de Git para ver las versiones

```
┌──(kali㉿kali)-[~/Desktop/drop-in]
└─$ git log --oneline 
.
.
.
.
e601368 important business work
95b31ba important business work
ec11eb0 important business work
5241c8d important business work
fadeca9 optimize file size of prod code
2dd4676 create top secret project
                                                                                                                  
┌──(kali㉿kali)-[~/Desktop/drop-in]
└─$ git show fadeca9 
commit fadeca9476b6713ec8cdda633aca9e9aebffc698
Author: picoCTF{@sk_th3_1nt3rn_e9957ce1} <ops@picoctf.com>
Date:   Sat Mar 9 21:09:11 2024 +0000

    optimize file size of prod code

diff --git a/message.py b/message.py
index 7df869a..326544a 100644
--- a/message.py
+++ b/message.py
@@ -1 +1 @@
-print("Hello, World!")
+print("Hello, World!"
```

### NOTAS ADICIONALES



### REFERENCIAS