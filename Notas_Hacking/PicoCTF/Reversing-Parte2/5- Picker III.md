### DESCRIPCIÓN

Can you figure out how this program works to get the flag?

Connect to the program with netcat:

$ nc saturn.picoctf.net 51213

The program's source code can be downloaded here.
### SOLUCIÓN

```
* Enter 'quit' to quit the program.
* Enter 'help' for this text.
* Enter 'reset' to reset the table.
* Enter '1' to execute the first function in the table.
* Enter '2' to execute the second function in the table.
* Enter '3' to execute the third function in the table.
* Enter '4' to execute the fourth function in the table.

Here's the current table:
  
1: print_table
2: read_variable
3: write_variable
4: getRandomNumber
==> 1
1: print_table
2: read_variable
3: write_variable
4: getRandomNumber
==> 3
Please enter variable name to write: getRandomNumber
Please enter new value of variable: win
==> 1
1: print_table
2: read_variable
3: write_variable
4: getRandomNumber
==> 4
0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x37 0x68 0x31 0x35 0x5f 0x31 0x35 0x5f 0x77 0x68 0x34 0x37 0x5f 0x77 0x33 0x5f 0x67 0x33 0x37 0x5f 0x77 0x31 0x37 0x68 0x5f 0x75 0x35 0x33 0x72 0x35 0x5f 0x31 0x6e 0x5f 0x63 0x68 0x34 0x72 0x67 0x33 0x5f 0x61 0x31 0x38 0x36 0x66 0x39 0x61 0x63 0x7d

┌──(kali㉿kali)-[~/Desktop/Reversing]
└─$ echo "70 69 63 6f 43 54 46 7b 37 68 31 35 5f 31 35 5f 77 68 34 37 5f 77 33 5f 67 33 37 5f 77 31 37 68 5f 75 35 33 72 35 5f 31 6e 5f 63 68 34 72 67 33 5f 61 31 38 36 66 39 61 63 7d" | xxd -r -p
picoCTF{7h15_15_wh47_w3_g37_w17h_u53r5_1n_ch4rg3_a186f9ac}  
```
### NOTAS ADICIONALES


### REFERENCIAS