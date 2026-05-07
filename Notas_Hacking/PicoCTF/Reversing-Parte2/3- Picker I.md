### DESCRIPCIÓN

This service can provide you with a random number, but can it do anything else?Connect to the program with netcat:`$ nc saturn.picoctf.net 50223`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/513/picker-I.py).
### SOLUCIÓN

```
┌──(kali㉿kali)-[~/Desktop/Reversing]
└─$ nc saturn.picoctf.net 50223

Try entering "getRandomNumber" without the double quotes...
==> win
0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x34 0x5f 0x64 0x31 0x34 0x6d 0x30 0x6e 0x64 0x5f 0x31 0x6e 0x5f 0x37 0x68 0x33 0x5f 0x72 0x30 0x75 0x67 0x68 0x5f 0x62 0x35 0x32 0x33 0x62 0x32 0x61 0x31 0x7d 

┌──(kali㉿kali)-[~/Desktop/Reversing]
└─$ python3 -c "print(bytes.fromhex('70 69 63 6f 43 54 46 7b 34 5f 64 31 34 6d 30 6e 64 5f 31 6e 5f 37 68 33 5f 72 30 75 67 68 5f 62 35 32 33 62 32 61 31 7d').decode('ascii'))"
picoCTF{4_d14m0nd_1n_7h3_r0ugh_b523b2a1}
```

### NOTAS ADICIONALES


### REFERENCIAS