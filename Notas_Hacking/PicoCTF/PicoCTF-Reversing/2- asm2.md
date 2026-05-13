### DESCRIPCIÓN

What does asm2(0x6,0x18) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://challenge-files.picoctf.net/c_fickle_tempest/884bf6f181649d8710b32dab0f0233a2784507ffcf65de41d0f3b28ad3ef6344/test.S)
### SOLUCIÓN

Se rastrea el flujo de ejecución de la función en ensamblador utilizando el argumento `0x36e` (almacenado en la pila en `[ebp+0x8]`).

1. **`<+7>`:** Compara el argumento (`0x36e`) con `0x6c8`. Al no ser mayor, la instrucción `jg` no salta.
    
2. **`<+16>`:** Compara el argumento (`0x36e`) con `0x36e`. Al ser exactamente iguales, la instrucción `jne` no salta.
    
3. **`<+25>`:** Mueve el argumento (`0x36e`) al registro de retorno `eax`.
    
4. **`<+28>`:** Suma `0x6` al valor en `eax`. Matemáticamente: `0x36e + 0x6 = 0x374`.
    
5. **`<+31>`:** La instrucción `jmp` realiza un salto incondicional al final de la función (`<+64>`), retornando el valor calculado.
    

**Flag:** `0x374`
### NOTAS ADICIONALES


### REFERENCIAS