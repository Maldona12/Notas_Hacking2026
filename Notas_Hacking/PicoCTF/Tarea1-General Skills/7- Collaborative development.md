### collaborative development

### DESCRIPCIÓN

My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/178/challenge.zip)

### SOLUCIÓN

Descargamos el archivo con wget
Descomprimimos con unzip
Entramos a la carpeta usando Cd
Usamos comandos de Git para ver las versiones

```
┌──(kali㉿kali)-[~/Desktop/drop-in]
└─$ git log --oneline
2258a0f (HEAD -> main) init flag printer
                                                                                                                  
┌──(kali㉿kali)-[~/Desktop/drop-in]
└─$ git show 2258a0f 
commit 2258a0f267d57e8b6025e2a020b77fac7a553c92 (HEAD -> main)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:54 2024 +0000

    init flag printer

diff --git a/flag.py b/flag.py
new file mode 100644
index 0000000..77d6cec
--- /dev/null
+++ b/flag.py
@@ -0,0 +1 @@
+print("Printing the flag...")
                                                                                                                  
┌──(kali㉿kali)-[~/Desktop/drop-in]
└─$ git branch -a   
  feature/part-1
  feature/part-2
  feature/part-3
* main
                                                                                                                  
┌──(kali㉿kali)-[~/Desktop/drop-in]
└─$ git show feature/part-1
commit 8eea0627726fc363246015cb4c7e927e70286e87 (feature/part-1)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:54 2024 +0000

    add part 1

diff --git a/flag.py b/flag.py
index 77d6cec..6e17fb3 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,2 @@
 print("Printing the flag...")
+print("picoCTF{t3@mw0rk_", end='')
\ No newline at end of file
                                                                                                                  
┌──(kali㉿kali)-[~/Desktop/drop-in]
└─$ git show feature/part-2
commit 05db9e274ff691e0f9fb492403b570629eb80aa9 (feature/part-2)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:54 2024 +0000

    add part 2

diff --git a/flag.py b/flag.py
index 77d6cec..7ab4e25 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,3 @@
 print("Printing the flag...")
+
+print("m@k3s_th3_dr3@m_", end='')
\ No newline at end of file
                                                                                                                  
┌──(kali㉿kali)-[~/Desktop/drop-in]
└─$ git show feature/part-3
commit 655c7bfebe9c221369ab00ac7374d0d4bd4d62a9 (feature/part-3)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:54 2024 +0000

    add part 3

diff --git a/flag.py b/flag.py
index 77d6cec..4f136da 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,3 @@
 print("Printing the flag...")
+
+print("w0rk_6c06cec1}")

```

picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_6c06cec1}
### NOTAS ADICIONALES



### REFERENCIAS