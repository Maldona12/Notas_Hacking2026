### DESCRIPCIÓN

Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

[Download disk image](https://artifacts.picoctf.net/c/164/disk.img.gz)

Access checker program: `nc saturn.picoctf.net 64889`
### SOLUCIÓN

El objetivo es analizar la tabla de particiones de una imagen de disco para extraer un valor específico (el tamaño de la partición de Linux) y validarlo en un servicio remoto.

1. **Descarga y descompresión:** Obtenemos la imagen de disco comprimida y la extraemos para obtener el archivo raw `.img`.
    ```
    wget https://artifacts.picoctf.net/c/164/disk.img.gz
    gzip -d disk.img.gz
    ```
    
2. **Análisis con `mmls`:** Utilizamos `mmls` (herramienta de _The Sleuth Kit_) para examinar el diseño de los medios (Media Management List). Esta herramienta muestra el inicio, fin y longitud de cada partición en sectores.

3. **Extracción del dato:** En la salida del comando, identificamos la partición de tipo **Linux (0x83)**:
    
```
┌──(kali㉿kali)-[~/Desktop/Forensic4]
└─$ mmls disk.img 
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)

```
 
La columna **Length** (longitud) nos indica que la partición tiene un tamaño de **202752** sectores.
 
4. **Obtención de la bandera:** Nos conectamos al servicio remoto vía `netcat` y proporcionamos el valor obtenido cuando el programa lo solicite. 
    ```
    nc saturn.picoctf.net 64889
    # What is the size of the Linux partition in the given disk image?
    # ==> 202752
    ```

5. **Resultado:** Al ingresar el valor correcto, el servidor responde con la bandera:
    - **Flag:** `picoCTF{mm15_f7w!}`

### NOTAS ADICIONALES


### REFERENCIAS