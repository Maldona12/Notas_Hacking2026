### Magikarp Ground Mission
  

### DESCRIPCIÓN

Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin.Login via `ssh` as `ctf-player` with the password, `8c606eb1` on the host `wily-courier.picoctf.net` and port `57897`.

### SOLUCIÓN



```
┌──(kali㉿kali)-[~/Desktop]
└─$ ssh ctf-player@wily-courier.picoctf.net -p 57897

ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ cat 1of3.flag.txt 
picoCTF{xxsh_

ctf-player@pico-chall$ cat instructions-to-2of3.txt 
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ cd /
ctf-player@pico-chall$ ls
2of3.flag.txt  dev                       lib    opt   sbin  usr
bin            etc                       lib64  proc  srv   var
boot           home                      media  root  sys
challenge      instructions-to-3of3.txt  mnt    run   tmp
ctf-player@pico-chall$ cat 2of3.flag.txt 
0ut_0f_//4t3r_
ctf-player@pico-chall$ 

ctf-player@pico-chall$ cat instructions-to-3of3.txt 
Lastly, ctf-player, go home... more succinctly `~`
ctf-player@pico-chall$ cd ~
ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
ctf-player@pico-chall$ cat 3of3.flag.txt 
0b24fc4f}ctf-player@pico-chall$ 

```

picoCTF{xxsh_0ut_0f_//4t3r_0b24fc4f}
### NOTAS ADICIONALES

  

### REFERENCIAS