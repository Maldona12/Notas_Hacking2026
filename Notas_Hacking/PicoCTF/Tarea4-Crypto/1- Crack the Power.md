### DESCRIPCIÓN

We received an encrypted message. The modulus is built from primes large enough that factoring them isn’t an option, at least not today. See if you can make sense of the numbers and reveal the flag.Download the [message](https://challenge-files.picoctf.net/c_amiable_citadel/3dcd347a6e654c8e7e4c10bd3ad888f73c14cb5375535053baef6ed5cbe2baa8/message.txt).
### SOLUCIÓN

```
  GNU nano 8.6                                   encry.py                                             
import decimal
decimal.getcontext().prec = 2000

n = 7182044538179166323847455947619004644121442847053964595557169963193125715155927639431459349236735>
e = 20
c = 6406374308104068575005667020962740799532346754425887123121060719047394997533981965273446408112118>

m_val = decimal.Decimal(c) ** (decimal.Decimal(1) / decimal.Decimal(e))

m = int(round(m_val))

flag_bytes = m.to_bytes((m.bit_length() + 7) // 8, byteorder='big')
print(flag_bytes.decode())
```

```
┌──(kali㉿kali)-[~/Desktop/Crypto4]
└─$ python3 encry.py
picoCTF{t1ny_e_46e014ec}
```
### NOTAS ADICIONALES


### REFERENCIAS