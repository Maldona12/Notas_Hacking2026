### binhexa

### DESCRIPCIÓN

How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 55447`

### SOLUCIÓN

```
┌──(kali㉿kali)-[~/Desktop]
└─$ nc titan.picoctf.net 55447  

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 01001101
Binary Number 2: 11010011


Question 1/6:
Operation 1: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 100100000    
Correct!

Question 2/6:
Operation 2: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: ^C
                                                                                                                  
┌──(kali㉿kali)-[~/Desktop]
└─$ nc titan.picoctf.net 55447

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 10010000
Binary Number 2: 00000110


Question 1/6:
Operation 1: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 00000011
Correct!

Question 2/6:
Operation 2: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10010110
Correct!

Question 3/6:
Operation 3: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10010110
Correct!

Question 4/6:
Operation 4: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 00000000
Correct!

Question 5/6:
Operation 5: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 00100000
Incorrect. Try again
Enter the binary result: 100100000
Correct!

Question 6/6:
Operation 6: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 1101100000
Correct!

Enter the results of the last operation in hexadecimal: 360

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_d9a7ddd2}


```

### NOTAS ADICIONALES

*Repasar las operaciones de nuevo*

### REFERENCIAS