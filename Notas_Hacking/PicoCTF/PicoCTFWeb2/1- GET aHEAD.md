### - GET aHEAD

### DESCRIPCIÓN

Find the flag being held on this server to get ahead of the competitionhttp://wily-courier.picoctf.net:59219/
### SOLUCIÓN

Usando la consola 

 ```
curl -X GET http://wily-courier.picoctf.net:59219/index.php
curl -X POST http://wily-courier.picoctf.net:59219/index.php
curl -X HEAD http://wily-courier.picoctf.net:59219/index.php
curl -I http://wily-courier.picoctf.net:59219/index.php

 ``` 

```
UZIEL_M-picoctf@webshell:~$ curl -X HEAD http://wily-courier.picoctf.net:59219/index.php
Warning: Setting custom HTTP method to HEAD with -X/--request may not work the 
Warning: way you want. Consider using -I/--head instead.
UZIEL_M-picoctf@webshell:~$ curl -I http://wily-courier.picoctf.net:59219/index.php
HTTP/1.1 200 OK
Date: Thu, 26 Feb 2026 03:31:03 GMT
Server: Apache/2.4.38 (Debian)
X-Powered-By: PHP/7.2.34
flag: picoCTF{r3j3ct_th3_du4l1ty_8b13f07}
Content-Type: text/html; charset=UTF-8
```

### NOTAS ADICIONALES


### REFERENCIAS