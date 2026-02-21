### Commitment Issues

### DESCRIPCIÓN

I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/139/challenge.zip)
### SOLUCIÓN

Descargamos el archivo con wget
Descomprimimos con unzip
Entramos a la carpeta usando Cd
Usamos comandos de Git para ver las versiones

```
┌──(kali㉿kali)-[~/Desktop/drop-in]
└─$ git log            
commit 7d3aa557ff7ba7d116badaf5307761efb3622249 (HEAD)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:25 2024 +0000

    create flag       
┌──(kali㉿kali)-[~/Desktop/drop-in]
└─$ git log --oneline
7d3aa55 (HEAD) create flag                             
┌──(kali㉿kali)-[~/Desktop/drop-in]
└─$ git show 7d3aa55    
commit 7d3aa557ff7ba7d116badaf5307761efb3622249 (HEAD)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:25 2024 +0000

    create flag

diff --git a/message.txt b/message.txt
new file mode 100644
index 0000000..3a71673
--- /dev/null
+++ b/message.txt
@@ -0,0 +1 @@
+picoCTF{s@n1t1z3_be3dd3da}

```

### NOTAS ADICIONALES

Aunque la bandera fue eliminada del estado actual del repositorio, Git conserva un historial completo de todos los commits. Al inspeccionar commits anteriores mediante `git log` y `git show`, fue posible recuperar el contenido eliminado y obtener la bandera.

### REFERENCIAS