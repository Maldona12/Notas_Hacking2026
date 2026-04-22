### DESCRIPCIÓN

We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/128/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
### SOLUCIÓN


 ```
 # leemos el mensaje y quitamos espacios y dividimos en partes
data = open('message.txt','r').read().strip().split(' ')

print(data)
flag = ''

# recorremos el mensaje para decodificarlo
for c in data:
        char = int(c) % 37
        print(f'{c:<5} - {char:<5} - ',end='')
         # mapeamos a letras en codigo ascii sumando 65
        if char>=0 and char<=25:
                s = chr(char+65)
        # mapeamos a numeros en codigo ascii (48 - 26)
        elif char>=26 and char<=35: 
                s= chr(char+22)
        elif char==36:
                s = '_'
        flag += s
        print(s)
print(f'\n{flag}')
 ``` 

  ```
  ┌──(kali㉿kali)-[~/Desktop/Crypto4]
└─$ python3 encry.py              
['165', '248', '94', '346', '299', '73', '198', '221', '313', '137', '205', '87', '336', '110', '186', '69', '223', '213', '216', '216', '177', '138']
165   - 17    - R
248   - 26    - 0
94    - 20    - U
346   - 13    - N
299   - 3     - D
73    - 36    - _
198   - 13    - N
221   - 36    - _
313   - 17    - R
137   - 26    - 0
205   - 20    - U
87    - 13    - N
336   - 3     - D
110   - 36    - _
186   - 1     - B
69    - 32    - 6
223   - 1     - B
213   - 28    - 2
216   - 31    - 5
216   - 31    - 5
177   - 29    - 3
138   - 27    - 1

R0UND_N_R0UND_B6B25531

  ```  


picoCTF{R0UND_N_R0UND_B6B25531}
### NOTAS ADICIONALES


### REFERENCIAS