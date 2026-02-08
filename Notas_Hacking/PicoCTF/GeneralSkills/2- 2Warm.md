
### 2Warm

DESCRIPCIÓN

Can you convert the number 42 (base 10) to binary  (base 2)?

SOLUCIÓN

## Solución 1 - Usando Calculadora 

https://masterplc.com/calculadora/convertir-decimal-a-binario/

42

picoctf{101010}

## Solución 2 - Convertir Manualmente 

42| 21 | 10 | 5 | 2 | 1 |        Par      ---->0
 0 |  1  |  0  | 1 | 0 | 1 |        Impar ----> 1

101010

picoctf{101010}

-------------------------------------------------------------
42 

| 64 | 32 | 16 | 8 | 4 | 2 | 1 |
|  0  |  1  |  0  | 1 | 0 | 1 | 0 |

101010

picoctf{101010}
## Solución 3 - Usar Python

```
Python 3.12.0 (tags/v3.12.0:0fb18b0, Oct  2 2023, 13:03:39) [MSC v.1935 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> bin(42)
'0b101010'
>>>
```

picoctf{101010}

NOTAS ADICIONALES

  Hay muchas maneras de convertir un numero decimal a Binario pero  para este caso creo que usando la calculadora es lo mas rápido.

REFERENCIAS