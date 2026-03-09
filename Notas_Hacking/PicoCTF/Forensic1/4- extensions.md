### [extensions](https://play.picoctf.org/practice/challenge/52)

### DESCRIPCIÓN

This is a really weird text file. Can you find the flag?Get the flag from [TXT](https://challenge-files.picoctf.net/c_fickle_tempest/31fe772e6a4c71e867af0b2a93818e06d8f8ebf8af2a9615495d00356ff576da/flag.txt).
### SOLUCIÓN

- Con el comando File ver que tipo de archivo es

```
┌──(kali㉿kali)-[~/Desktop/Forensic/extension]
└─$ file flag.png 
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced

```

- Cambiar la extensión del archivo para que coincida 

 - Copiar la bandera que viene en la imagen:

picoCTF{now_you_know_about_extensions}
### NOTAS ADICIONALES


### REFERENCIAS