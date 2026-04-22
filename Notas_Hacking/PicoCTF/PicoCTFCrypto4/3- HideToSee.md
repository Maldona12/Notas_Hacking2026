### DESCRIPCIÓN

How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/235/atbash.jpg).
### SOLUCIÓN

- Abrimos la imagen, y vemos la palabra `abatsh cipher` que es el nombre de un algortimo de cifrado
- Extraemos el texto dentro de la imagen con `steghide` y abrimos la imagen

`sudo apt install steghide steghide --extract -sf atbash.jpg`

- mostramos el texto encriptado dentro del archivo de texto que extragimos

```
┌──(kali㉿kali)-[~/Desktop/Crypto4]
└─$ cat encrypted.txt
krxlXGU{zgyzhs_xizxp_92533667}
```

- Desencriptamos en ciberchef usando el nombre del algoritmo que descubrimos en la. imagen : `atbash`

``picoCTF{atbash_crack_92533667}``

### NOTAS ADICIONALES


### REFERENCIAS