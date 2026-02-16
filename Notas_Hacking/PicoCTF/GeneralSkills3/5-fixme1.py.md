### fixme1.py


### DESCRIPCIÓN

Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/27/fixme1.py)

### SOLUCIÓN

Correr el código para ver el error, modificar el código y correrlo:

```
┌──(kali㉿kali)-[~/Desktop]
└─$ python3 fixme1.py   
  File "/home/kali/Desktop/fixme1.py", line 19
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
                                                                             
┌──(kali㉿kali)-[~/Desktop]
└─$ nano fixme1.py   
                                                                             
┌──(kali㉿kali)-[~/Desktop]
└─$ python3 fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}

```


### NOTAS ADICIONALES



### REFERENCIAS