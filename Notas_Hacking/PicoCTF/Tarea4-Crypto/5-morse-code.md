### DESCRIPCIÓN

Morse code is well known. Can you decrypt this?Download the file [here](https://artifacts.picoctf.net/c/79/morse_chal.wav).Wrap your answer with picoCTF{}, put underscores in place of pauses, and use all lowercase.
### SOLUCIÓN

- Abrí el archivo `.wav` en **Audacity** para hacer un análisis visual de la forma de onda.
    
- Haciendo zoom, los patrones eran claros y constantes:
    
    - Pulsos cortos = Puntos (`.`)
        
    - Pulsos largos = Rayas (`-`)
- El mensaje emulaba la primera frase enviada por telégrafo: _"What hath God wrought"_.
    
- Sin embargo, al traducir los picos exactos, sustituyeron letras clave por números muy específicos para evitar que los participantes adivinaran la frase sin terminar de traducir:
    
    - En lugar de la **G** (`--.`), el audio tiene un **9** (`----.`).
        
    - En lugar de la **R** (`.-.`), el audio tiene un **2** (`..---`).
        
- El texto sin procesar resultó ser: `W H 4 7 H 4 7 H 9 0 D W 2 0 U 9 H 7`
    

**Formateo de la Bandera:**

- Aplicando las reglas del reto (minúsculas y guiones bajos en los espacios largos): `wh47_h47h_90d_w20u9h7`

Flag: `picoCTF{wh47_h47h_90d_w20u9h7}`
### NOTAS ADICIONALES


### REFERENCIAS