### Static ain't always noise
  
### DESCRIPCIÓN

 Can you look at the data in this binary? The bash script might help![static](https://challenge-files.picoctf.net/c_wily_courier/34dfb62cf2c94a618c7cdc292ff1c4062b104773695071e9a16ab25ad8cc935c/static), [ltdis.sh](https://challenge-files.picoctf.net/c_wily_courier/34dfb62cf2c94a618c7cdc292ff1c4062b104773695071e9a16ab25ad8cc935c/ltdis.sh)
### SOLUCIÓN

  ┌──(kali㉿kali)-[~/Desktop]
└─$ chmod +x ltdis.sh  
                                                                             
┌──(kali㉿kali)-[~/Desktop]
└─$ ./ltdis.sh 
Attempting disassembly of  ...
objdump: 'a.out': No such file
objdump: section '.text' mentioned in a -j option, but not found in any input file
Disassembly failed!
Usage: ltdis.sh <program-file>
Bye!
                                                                             
┌──(kali㉿kali)-[~/Desktop]
└─$ ./ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
                                                                             
┌──(kali㉿kali)-[~/Desktop]
└─$ strings static | grep pico
picoCTF{d15a5m_t34s3r_20335e41}
                                                                             
┌──(kali㉿kali)-[~/Desktop]
└─$ 


### NOTAS ADICIONALES

  

### REFERENCIAS