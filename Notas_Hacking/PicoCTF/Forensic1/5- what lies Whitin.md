### [What Lies Within](https://play.picoctf.org/practice/challenge/74)

### Descripción

There's something in the [building](https://challenge-files.picoctf.net/c_fickle_tempest/c0eec6af0f04316e2bdc4a9f095afd0e2d0121f5e543dbc4a65bb0038d72a993/buildings.png). Can you retrieve the flag?
### SOLUCIÓN

- Para resolver este reto, se utilizó la herramienta **zsteg**, que es un detector de esteganografía especializado en formatos PNG y BMP.
 
 ```
 ┌──(kali㉿kali)-[~/Desktop/Forensic/whatLies]
└─$ zsteg -a buildings.png buildings.png | grep pico
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
 ```
### NOTAS ADICIONALES


### REFERENCIAS