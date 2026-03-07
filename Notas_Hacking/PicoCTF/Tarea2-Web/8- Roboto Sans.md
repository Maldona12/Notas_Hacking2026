### [Roboto Sans](https://play.picoctf.org/practice/challenge/291)

### DESCRIPCIÓN

The flag is somewhere on this web application not necessarily on the website. Find it. Check [this](http://saturn.picoctf.net:49873/) out.
### SOLUCIÓN

- Acceder al archivo `robots.txt` añadiendo `/robots.txt` a la URL del reto.

- Analizar las líneas de texto sospechosas que no parecen rutas comunes. Se identifican dos cadenas que parecen estar codificadas:

	- `ZmxhZzEudHh0`  
	- `anMvbXlmaWxlLnR4dA==`

- Utilizar la terminal de **Kali Linux** o un decodificador online para traducir las cadenas de **Base64**:

    - `echo "ZmxhZzEudHh0" | base64 -d` -> Resultado: `flag1.txt`        
    - `echo "anMvbXlmaWxlLnR4dA==" | base64 -d` -> Resultado: `js/myfile.txt`
   
- Probar las rutas decodificadas en el navegador. Al intentar acceder a `http://saturn.picoctf.net:49873/js/myfile.txt`, el servidor entrega la bandera.

picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}


### NOTAS ADICIONALES


### REFERENCIAS