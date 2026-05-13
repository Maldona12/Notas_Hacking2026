### DESCRIPCIÓN

What does asm1(0x36e) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://challenge-files.picoctf.net/c_fickle_tempest/742701d2dc84a01fe69c48228c14feafdcd3658f83e99b887c550bed0302419e/test.S)
### SOLUCIÓN

El reto nos pide rastrear el flujo de ejecución de la función en ensamblador `asm1` cuando se le pasa el argumento `0x36e`. En la convención de llamadas de 32 bits, el argumento se almacena en la pila en la dirección `[ebp+0x8]`.

Rastreando el código paso a paso con el valor `0x36e`:

1. **`<+7>`:** Compara el argumento (`0x36e`) con `0x6c8`.
    
2. **`<+14>`:** `jg` (Jump if Greater / Salta si es mayor). Como `0x36e` no es mayor que `0x6c8`, **no salta**.
    
3. **`<+16>`:** Compara el argumento (`0x36e`) con `0x36e`.
    
4. **`<+23>`:** `jne` (Jump if Not Equal / Salta si no es igual). Como son exactamente iguales, **no salta**.
    
5. **`<+25>`:** `mov eax, DWORD PTR [ebp+0x8]`. Mueve nuestro argumento (`0x36e`) al registro `eax` (que es donde se guarda el valor de retorno de una función).
    
6. **`<+28>`:** `add eax, 0x6`. Le suma `0x6` al valor en `eax`. Matemáticamente en hexadecimal: `0x36e + 0x6 = 0x374`.
    
7. **`<+31>`:** `jmp 0x11ed <asm1+64>`. Hace un salto incondicional directo a la línea 64, donde hace `pop ebp` y `ret` (retorna el programa entregando el valor de `eax`).
    

**Flag:** `0x374`
### NOTAS ADICIONALES


### REFERENCIAS