### DESCRIPCIÓN

What does asm3(0xb58568e8,0xc63ab2a1,0xf9d33ef4) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://challenge-files.picoctf.net/c_fickle_tempest/b3fee52f11c2963c3f6008623c66d7c0906ab439f927132ac7fbc1d53f83c4ee/test.S)
### SOLUCIÓN

Se analiza la función rastreando el estado de la memoria y los registros. Es fundamental recordar que la arquitectura x86 almacena la memoria en formato _Little-Endian_ (los bytes menos significativos se guardan en las direcciones más bajas).

Los argumentos se ubican en la pila así: Arg1 en `[ebp+0x8]` (`0xb58568e8`), Arg2 en `[ebp+0xc]` (`0xc63ab2a1`), y Arg3 en `[ebp+0x10]` (`0xf9d33ef4`).

1. **`<+7>`:** `xor eax, eax`. Inicializa el registro `eax` completamente en `0x00000000`.
    
2. **`<+9>`:** `mov ah, BYTE PTR [ebp+0xb]`. Toma el cuarto byte de Arg1 (`0xb5`) y lo pone en la parte alta de 8 bits (`ah`). `eax` = `0x0000b500`.
    
3. **`<+12>`:** `shl ax, 0x10`. Desplaza `ax` a la izquierda 16 posiciones. Como `ax` es de 16 bits, desplazarlo 16 espacios empuja todos sus bits fuera del registro, dejándolo en `0x0000`. `eax` vuelve a ser `0x00000000`.
    
4. **`<+16>`:** `sub al, BYTE PTR [ebp+0xd]`. Resta el segundo byte de Arg2 (`0xb2`) a `al` (`0x00`). Matemáticamente: `0x00 - 0xb2 = -0xb2`. En un registro de 8 bits, esto hace "underflow" y resulta en `0x4e`. `eax` = `0x0000004e`.
    
5. **`<+19>`:** `add ah, BYTE PTR [ebp+0xc]`. Suma el primer byte de Arg2 (`0xa1`) a `ah` (`0x00`). `0x00 + 0xa1 = 0xa1`. `eax` = `0x0000a14e`.
    
6. **`<+22>`:** `xor ax, WORD PTR [ebp+0x10]`. Aplica la operación lógica XOR entre `ax` (`0xa14e`) y los primeros 2 bytes (WORD) de Arg3. Por Little-Endian, los bytes `f4` y `3e` forman la palabra `0x3ef4`. Operación: `0xa14e XOR 0x3ef4 = 0x9fba`.
    
7. **`<+27>`:** Retorna el valor contenido en la parte baja del registro.

**Flag:** `0x9fba`
### NOTAS ADICIONALES


### REFERENCIAS