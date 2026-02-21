### binary search

### DESCRIPCIÓN

Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/20/challenge.zip)

`ssh -p 63160 ctf-player@atlas.picoctf.net`Using the password `6abf4a82`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!

### SOLUCIÓN

Usar búsqueda binaria:

Iniciar rango: 1 – 1000

Calcular punto medio:

mid = (min + max) // 2

Ajustar rango según la respuesta

Repetir hasta encontrar el número

```
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Lower! Try again.
Enter your guess: 250
Higher! Try again.
Enter your guess: 375
Lower! Try again.
Enter your guess: 312
Lower! Try again.
Enter your guess: 281
Lower! Try again.
Enter your guess: 265
Lower! Try again.
Enter your guess: 257
Lower! Try again.
Enter your guess: 253
Higher! Try again.
Enter your guess: 255
Lower! Try again.
Enter your guess: 254
Congratulations! You guessed the correct number: 254
Here's your flag: picoCTF{g00d_gu355_bee04a2a}
Connection to atlas.picoctf.net closed.
```

### NOTAS ADICIONALES



### REFERENCIAS