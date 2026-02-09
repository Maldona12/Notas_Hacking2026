### Nice netcat...

### DESCRIPCIÓN

There is a nice program that you can talk to by using this command in a shell:$ nc wily-courier.picoctf.net 61323, but it doesn't speak English...
### SOLUCIÓN

 Al ingresar el comando "nc wily-courier.picoctf.net 61323" arroja esto:


```
┌──(kali㉿kali)-[~]
└─$ nc wily-courier.picoctf.net 61323~  
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
102 
55 
97 
54 
101 
125 
10 
                                                                             
┌──(kali㉿kali)-[~]
└─$ 
```

Con la pista y al ver los números podemos asumir que se trata de código ASCII del cual revelara la bandera, por lo tanto con alguna función en Python podemos convertirlos todos:

```
>>> nums = [112,105,99,111,67,84,70,123,103,48,48,100,95,107,49,116,116,121,33,95,110,49,99,51,95,107,49,116,116,121,33,95,102,55,97,54,101,125]
>>> print(''.join(chr(n) for n in nums))
picoCTF{g00d_k1tty!_n1c3_k1tty!_f7a6e}
>>>
```

### NOTAS ADICIONALES

  Quizá haya una forma de optimizar el código en Python para la conversión pero de momento hacerlo así se me hace lo mas sencillo 
### REFERENCIAS