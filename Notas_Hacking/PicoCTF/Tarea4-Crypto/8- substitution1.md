### DESCRIPCIÓN

A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again.Download the message [here](https://artifacts.picoctf.net/c/181/message.txt).
### SOLUCIÓN

A diferencia del reto anterior, aquí no nos dan la llave. Siendo un cifrado de sustitución simple. Para resolverlo, utilizamos **Análisis de Frecuencias** y reconocimiento de patrones (lo que en criptografía se llama _Ataque de Texto Plano Conocido_).

1. Al ver la cadena `cbzjZWD{...}` al final, sabemos por el formato del reto que esto equivale a `picoCTF{...}`. Esto nos regala 7 letras de la clave (c=p, b=i, z=c, j=o, Z=C, W=T, D=F).
    
2. Sabiendo que `ZWD` = `CTF`, podemos deducir que la primera palabra del texto `ZWDg` significa `CTFs` (por lo tanto, g=s).
    
3. Buscando palabras cortas comunes de tres letras, descubrimos que `wex` significa `the` y `afx` significa `are`.
    
4. Al ir reemplazando estas letras conocidas en el resto del texto, se revelan palabras como "capture the flag" o "computer security", permitiendo reconstruir el abecedario completo.
    

Al aplicar estas correspondencias a la parte interna de la bandera cifrada (`DF3LP3VZS_4774ZN5_4F3_Z001_4871X6DT`), descubrimos el mensaje en leetspeak _"Frequency attacks are cool"_ (los ataques de frecuencia son geniales) seguido de una cadena hexadecimal.

Flag:  `picoCTF {FR3QU3NCY_4774CK5_4R3_C001_4871E6FB}`
### NOTAS ADICIONALES


### REFERENCIAS