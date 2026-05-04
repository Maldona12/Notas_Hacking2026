### DESCRIPCIÓN

It seems that another encrypted message has been intercepted. The encryptor seems to have learned their lesson though and now there isn't any punctuation! Can you still crack the cipher?Download the message [here](https://artifacts.picoctf.net/c/114/message.txt).
### SOLUCIÓN

Al igual que los retos anteriores, es un cifrado de sustitución simple (monoalfabético), pero esta vez han eliminado los espacios para dificultar las herramientas automáticas y forzarte a usar un "Análisis de N-gramas" (buscar secuencias de letras comunes).

1. Identificamos el formato de la bandera al final: `vqkmKFL{...}` se traduce directamente como `picoCTF{...}`. Esto nos regala las primeras letras (v=p, q=i, k=c, m=o, etc.).
    
2. Usando esas letras conocidas, buscamos secuencias largas en el texto. Se revelan palabras clave del contexto, como `kmuvafjdsjkadqftkmuvjfqfqmg` que se descifra como `computersecuritycompetition` (competencia de seguridad informática), y `cjwwjsfxhwqsnjy` que se descifra como `wellestablished` (bien establecido).
    
3. Mapeando este abecedario deducido al interior de la llave, obtenemos el mensaje en _leetspeak_: _"N-gram analysis is tedious"_ (el análisis de n-gramas es tedioso), seguido de una cadena hexadecimal donde las letras (J, X) también fueron sustituidas por su equivalente real (E, A).
    

Flag: `picoCTF{N6R4M_4N41Y515_15_73D10U5_42EA1770}`
### NOTAS ADICIONALES


### REFERENCIAS