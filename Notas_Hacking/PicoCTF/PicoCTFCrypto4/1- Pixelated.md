### DESCRIPCIÓN

I have these 2 images, can you make a flag out of them?[scrambled1.png](https://challenge-files.picoctf.net/c_wily_courier/948209c9bfbe84d9dce56e1bbd6d7eb768730f7ad07bc425c493f224d0e47ccf/scrambled1.png) [scrambled2.png](https://challenge-files.picoctf.net/c_wily_courier/948209c9bfbe84d9dce56e1bbd6d7eb768730f7ad07bc425c493f224d0e47ccf/scrambled2.png)
### SOLUCIÓN

### Solución 1 - con `stegsolve`

- Descargamos `stegsolve` :

`cd /opt sudo wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar sudo chmod +x stegsolve.jar java -jar /opt/stegsolve.jar` 

- Abrimos la primer imagen
    
    - `File - Open`
    
- La combinamos con la segunda
    
    - `Analyse - Image Combiner`
    
- Usamos los iconos de flecha en la parte de abajo para elegir el tipo de combinación hasta encontrar AND
- Opcionalmente grabamos el archivo con la bandera

picoCTF{8cdf93c3}
### NOTAS ADICIONALES


### REFERENCIAS