### Codebook

### DESCRIPCIÓN

Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/1/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/1/codebook.txt)

### SOLUCIÓN

Descargar el código con el wget, asegurar que ambos archivos esten en la misma carpeta con el comando "ls" después usar python para ejecutarlo:

```
┌──(kali㉿kali)-[~/Desktop]
└─$ ls
Addadshashanammu      enc_flag   runme.py
Addadshashanammu.zip  files      static
big-zip-files         files.zip  static.ltdis.strings.txt
big-zip-files.zip     file.txt   static.ltdis.x86_64.txt
codebook.txt          flag       strings
code.py               ltdis.sh   warm
                                                                             
┌──(kali㉿kali)-[~/Desktop]
└─$ python3 code.py 
picoCTF{c0d3b00k_455157_d9aa2df2}


```

### NOTAS ADICIONALES



### REFERENCIAS