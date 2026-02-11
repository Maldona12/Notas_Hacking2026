### Plumbing 

### DESCRIPCIÓN

Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag?Connect to fickle-tempest.picoctf.net 51521.
### SOLUCIÓN

  Al ingresar esta vez al servidor  "fickle-tempest.picoctf.net 5152" aparece mucho texto del cual no se puede distinguir cual es la bandera correcta. La pista menciona que se debe de usar un "pipe" por lo cual se puede deducir que se puede otro comando a la vez que se consulta el servidor para encontrar la bandera.

Esta vez vuelvo a ingresar pero combinándolo con el comando grep anteriormente utilizado:

nc fickle-tempest.picoctf.net 51521 | grep picoCTF

El resultado es:

picoCTF{digital_plumb3r_8c8f3412}
### NOTAS ADICIONALES

* Pipe | redirige la salida de un comando a la entrada de otro 
* > redirige la salida de un comando a un archivo de texto 

### REFERENCIAS