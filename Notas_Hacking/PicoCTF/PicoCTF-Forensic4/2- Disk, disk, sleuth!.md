### DESCRIPCIÓN

Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image. [dds1-alpine.flag.img.gz](https://challenge-files.picoctf.net/c_wily_courier/8643b47c3c19e52e891a4684258e1d1cbb65094afa9cf81317b563004a739653/dds1-alpine.flag.img.gz)
### SOLUCIÓN

- **Preparación del archivo:** Primero, descargamos el archivo comprimido y utilizamos `gzip` para descomprimir la imagen de disco (`.img`).

    ```
    wget https://challenge-files.picoctf.net/c_wily_courier/8643b47c3c19e52e891a4684258e1d1cbb65094afa9cf81317b563004a739653/dds1-alpine.flag.img.gz
    gzip -d dds1-alpine.flag.img.gz
    ```

- **Análisis del tipo de archivo:** Al verificar el archivo resultante con `file`, confirmamos que se trata de un sector de arranque DOS/MBR con una partición Linux activa.

    ```
    file dds1-alpine.flag.img
    # dds1-alpine.flag.img: DOS/MBR boot sector; partition 1 : ID=0x83...
    ```

- **Uso de The Sleuth Kit (TSK):** Para analizar la imagen sin montarla, instalamos `sleuthkit`, una colección de herramientas de línea de comandos que permite investigar imágenes de disco de forma forense.
    ```
    sudo apt install -y sleuthkit
    ```

- **Extracción de cadenas y filtrado:** Utilizamos la herramienta `srch_strings` (que es parte de Sleuth Kit y es más potente que el comando `strings` estándar para imágenes de disco) para buscar secuencias de caracteres imprimibles. Filtramos el resultado con `grep` para encontrar el prefijo de la bandera:
    ```
    srch_strings dds1-alpine.flag.img | grep pico
    ```

- **Resultado:** Entre los símbolos del kernel y rutas de archivos, se localizó la bandera en una línea de configuración o mensaje de arranque:
    
    - **Flag:** `picoCTF{f0r3ns1c4t0r_n30phyt3_5e56e786}`
### NOTAS ADICIONALES

**¿Por qué usar `srch_strings` en lugar de `strings`?** Aunque en este reto en particular `strings` podría haber funcionado, `srch_strings` es preferible en análisis forense porque permite buscar en áreas del disco que a veces son omitidas por herramientas estándar, además de permitir la especificación de offsets de sectores y el manejo de diferentes codificaciones de caracteres (como Unicode) de forma más robusta dentro de imágenes de disco crudas.
### REFERENCIAS