### DESCRIPCIÓN

This service provides you an encrypted flag. Can you decrypt it with just N & e?

Additional details will be available after launching your challenge instance.
### SOLUCIÓN

```
from Crypto.Util.number import inverse, long_to_bytes

N = 20263046288988298642613925549766983159307681996611135812028553402183697779008864815261968149198659495100427434451380857016052635190048034077757134027970122
e = 65537
c = 2290467905689410483744580607410022208727909659005637180308149797404677225084696713130875940622766475870826458085379766087029570707357694098490474669126761

# factor trivial
p = 2
q = N // 2

phi = (p - 1) * (q - 1)

d = inverse(e, phi)

m = pow(c, d, N)

print(long_to_bytes(m))
```

Flag:  picoCTF{tw0_1$_pr!m37dbe6984}'
### NOTAS ADICIONALES


### REFERENCIAS