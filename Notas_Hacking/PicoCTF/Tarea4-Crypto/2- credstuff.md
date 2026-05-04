### DESCRIPCIÓN

We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it?Download the leak [here](https://artifacts.picoctf.net/c/151/leak.tar).The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.
### SOLUCIÓN

```
┌──(kali㉿kali)-[~/Desktop/Crypto4]
└─$ tar -xvf leak.tar     
leak/
leak/passwords.txt
leak/usernames.txt
┌──(kali㉿kali)-[~/Desktop/Crypto4]
└─$ cd leak       
┌──(kali㉿kali)-[~/Desktop/Crypto4/leak]
└─$ grep -n "cultiris" usernames.txt
378:cultiris
┌──(kali㉿kali)-[~/Desktop/Crypto4/leak]
└─$ sed -n '378p' passwords.txt
cvpbPGS{P7e1S_54I35_71Z3}
┌──(kali㉿kali)-[~/Desktop/Crypto4/leak]
└─$ echo "cvpbPGS{P7e1S_54I35_71Z3}" | tr 'A-Za-z' 'N-ZA-Mn-za-m'
picoCTF{C7r1F_54V35_71M3}
```




### NOTAS ADICIONALES


### REFERENCIAS