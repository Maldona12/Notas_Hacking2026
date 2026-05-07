### DESCRIPCIÓN

Can you figure out how this program works to get the flag?

Connect to the program with netcat:

$ nc saturn.picoctf.net 62919

The program's source code can be downloaded here. The binary can be downloaded here.
### SOLUCIÓN

```
┌──(kali㉿kali)-[~/Desktop/Reversing]
└─$ nm picker-IV | grep win
000000000040129e T win

┌──(kali㉿kali)-[~]
└─$ nc saturn.picoctf.net 62919
Enter the address in hex to jump to, excluding '0x': 0x000000000040129e
You input 0x40129e
You won!
picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_14bc5444}

```
### NOTAS ADICIONALES


### REFERENCIAS