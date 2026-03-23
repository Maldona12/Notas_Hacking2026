### RETO

### DESCRIPCIÓN

Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/138/disk.flag.img.gz)
### SOLUCIÓN

A diferencia de los retos anteriores, esta imagen de disco contiene varias particiones. El objetivo es identificar cuál de ellas contiene el sistema de archivos principal y localizar la bandera explorando sus directorios.

1. **Preparación de la imagen:** Descomprimimos el archivo para obtener la imagen raw.

    ```
    gzip -d disk.flag.img.gz
    ```

2. **Identificación de Particiones con `mmls`:** Examinamos la tabla de particiones para entender la estructura del disco.

    ```
    mmls disk.flag.img
    ```

    - **Partición 1 (Offset 2048):** Linux (0x83) - Tamaño pequeño, probablemente `/boot`.
        
    - **Partición 2 (Offset 206848):** Swap - Memoria de intercambio.
        
    - **Partición 3 (Offset 360448):** Linux (0x83) - Tamaño mayor, probablemente la partición raíz (`/`).

3. **Exploración del Sistema de Archivos con `fls`:** Primero exploramos la partición 3 (offset 360448) buscando directorios sospechosos o la bandera directamente. Usamos el flag `-r` para una búsqueda recursiva.

    ```
    fls -o 360448 -r disk.flag.img
    ```

    _(Tras navegar por los resultados, se identifica un inodo sospechoso o un archivo que contiene la bandera)._

4. **Extracción del contenido con `icat`:** Una vez localizado el inodo del archivo de la bandera (en este caso, el inodo **2371**), utilizamos `icat` especificando el offset de la partición para leer su contenido sin montar el disco.

    ```
    icat -o 360448 disk.flag.img 2371
    ```

5. **Resultado:** El comando devuelve el texto plano almacenado en ese sector del disco:
    - **Flag:** `picoCTF{by73_5urf3r_2f22df38}`
### NOTAS ADICIONALES


### REFERENCIAS