### DESCRIPCIÓN

🥛 http://wily-courier.picoctf.net:58694/

### SOLUCIÓN

El reto presenta un sitio web con una animación interactiva. Al inspeccionar los recursos de la red o el código fuente, se identifica una imagen de gran tamaño que sirve como base para el reto.

1. **Obtención del recurso:** Descargamos la imagen `concat_v.png` desde el servidor del reto. El archivo tiene un tamaño considerable (aprox. 17MB), lo que sugiere que contiene datos ocultos.
    ```
    wget http://wily-courier.picoctf.net:58694/concat_v.png
    ```

2. **Preparación de herramientas:** Para analizar la esteganografía en archivos PNG, la herramienta más efectiva es `zsteg`. Debido a que la imagen es muy grande, es necesario aumentar el tamaño de la pila (stack) de la máquina virtual de Ruby para evitar errores de memoria durante el procesamiento.
    ```
    # Instalación de la herramienta
    sudo gem install zsteg
    
    # Configuración de memoria para procesar imágenes grandes
    export RUBY_THREAD_VM_STACK_SIZE=500000000
    ```    
2. **Análisis de bits (LSB):** Ejecutamos `zsteg` sobre la imagen. Esta herramienta analiza los canales de color (R, G, B) buscando patrones de datos en los bits menos significativos (Least Significant Bits), que es donde se suelen ocultar mensajes sin alterar la apariencia visual de la imagen.
    ```
    zsteg concat_v.png
    ```

3. **Resultados:** El escaneo reveló texto plano oculto en el canal azul (blue), bit 1, orden LSB:

```
┌──(kali㉿kali)-[~/Desktop/Forensic4]
└─$ zsteg concat_v.png  
imagedata           .. text: "\n\n\n\n\n\n\t\t"
chunk:0:IHDR        .. file: Adobe Photoshop Color swatch, version 0, 1280 colors; 1st RGB space (0), w 0xb9a0, x 0x802, y 0, z 0; 2nd HSB space (1), w 0, x 0, y 0, z 0                                                                                                                                                                    
b1,b,lsb,xy         .. text: "picoCTF{imag3_m4n1pul4t10n_sl4p5}\n"
b1,bgr,lsb,xy       .. <wbStego size=0x941a5b ext=nil data="\xB6\xAD\xB6}\xDB\xB2lR\x7F\xDF\x86\xB7c\xFC\xFF\xBF\x02Zr\x8E\xE2Z\x12\xD8q\xE5&MJ-X:\xB5\xBF\xF7\x7F\xDB\xDFI\bm\xDB\xDB\x80m\x00\x00\x00\xB6m\xDB\xDB\xB6\x00\x00\x00\xB6\xB6\x00m\xDB\x12\x12m\xDB\xDB\x00\x00\x00\x00\x00\xB6m\xDB\x00\xB6\x00\x00\x00\xDB\xB6mm\xDB\xB6\xB6\x00\x00\x00\x00\x00m\xDB" even=true hdr=nil enc=nil mix=true controlbyte="[">                                                                                       
b2,r,lsb,xy         .. text: ["U" repeated 8 times]
b2,r,msb,xy         .. file: VISX image file
b2,g,lsb,xy         .. file: VISX image file
b2,g,msb,xy         .. file: SoftQuad DESC or font file binary - version 15722
b2,b,msb,xy         .. text: "UfUUUU@UUU"
b4,r,lsb,xy         .. text: "\"\"\"\"\"#4D"
b4,r,msb,xy         .. text: "wwww3333"
b4,g,lsb,xy         .. text: "wewwwwvUS"
b4,g,msb,xy         .. text: "\"\"\"\"DDDD"
b4,b,lsb,xy         .. text: "vdUeVwweDFw"
b4,b,msb,xy         .. text: "UUYYUUUUUUUU"

```
### NOTAS ADICIONALES


### REFERENCIAS