### Based
  
### DESCRIPCIÓN

To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337?Connect with nc fickle-tempest.picoctf.net 52832

### SOLUCIÓN

Para resolver la primera parte del reto se obtuvo el siguiente texto:

```
└─$ nc fickle-tempest.picoctf.net 52832
Let us see how data is stored
test
Please give the 01100001 01101110 01101001 01101101 01100001 01110100 01101001 01101111 01101110 as a word.
...
you have 45 seconds.....


```

Para el cual busque este código para poder hacer la conversión de una manera rápida usando Python:

```
while True:
    data = input("Pega los binarios separados por espacio: ")
    try:
        print("Resultado:", ''.join(chr(int(b, 2)) for b in data.split()))
    except:
        print("Entrada inválida")

Pega los binarios separados por espacio: 01100110 01100001 01101100 01100011 01101111 01101110
Resultado: falcon

```

Creí que me daría la bandera pero después de haber convertido de binario a chr obtuve otro mensaje pero esta vez en Octal para el cual tuve que buscar otro código que me ayudara a convertir desde distintas bases:

```
while True:

    data = input("Ingresa datos: ").split()

    result = ""

    for x in data:

        # Binario (8 bits)

        if all(c in "01" for c in x) and len(x) == 8:

            result += chr(int(x, 2))

        # Octal con prefijo 'o'

        elif x.startswith("o") and x[1:].isdigit():

            result += chr(int(x[1:], 8))

        # Hexadecimal (soporta strings largos sin espacios)

        elif all(c in "0123456789abcdefABCDEF" for c in x):

            try:

                result += bytes.fromhex(x).decode()

            except:

                result += chr(int(x, 16))

        # Decimal

        elif x.isdigit():

            result += chr(int(x))

    print("Resultado:", result)
```

Con ayuda del código anterior fue sencillo resolver los diferentes mensajes que me mando:

```
┌──(kali㉿kali)-[~]
└─$ nc fickle-tempest.picoctf.net 52832
Let us see how data is stored
animation
Please give the 01100001 01101110 01101001 01101101 01100001 01110100 01101001 01101111 01101110 as a word.
...
you have 45 seconds.....

Input:
animation
Please give me the  o143 o157 o155 o160 o165 o164 o145 o162 as a word.
Input:
computer
Please give me the 737472656574 as a word.
Input:
street
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_563BAF26}


```

### NOTAS ADICIONALES

  

### REFERENCIAS