### chrono

### DESCRIPCIÓN

How to automate tasks to run at intervals on linux servers?Use ssh to connect to this server:

```
Server: saturn.picoctf.net
Port: 50241
Username: picoplayer 
Password: kZx-HVJKu8
```

### SOLUCIÓN

Buscar en cron

```
crontab -l
/etc/crontab

picoplayer@challenge:~$ cat /etc/crontab
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_5b7059d0}

```
### NOTAS ADICIONALES

- `cron` es el servicio que permite programar tareas en Linux.
- `crontab` es el archivo donde se definen esas tareas.
- `/etc/crontab` es el archivo global del sistema.

### REFERENCIAS