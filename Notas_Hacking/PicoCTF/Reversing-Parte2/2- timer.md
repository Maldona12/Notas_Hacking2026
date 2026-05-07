### DESCRIPCIÓN

You will find the flag after analysing this apkDownload [here](https://artifacts.picoctf.net/c/449/timer.apk).
### SOLUCIÓN

```
┌──(kali㉿kali)-[~/Desktop/Reversing]
└─$ unzip timer.apk -d timer_folder 

┌──(kali㉿kali)-[~/Desktop/Reversing]
└─$ grep -r "pico" timer_folder 
grep: timer_folder/classes3.dex: binary file matches

┌──(kali㉿kali)-[~/Desktop/Reversing]
└─$ strings timer_folder/classes3.dex | grep "pico"   
*picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}

``` 
### NOTAS ADICIONALES


### REFERENCIAS