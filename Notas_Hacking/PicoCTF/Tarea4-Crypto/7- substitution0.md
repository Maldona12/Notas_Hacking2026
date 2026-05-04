### DESCRIPCIÓN

A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher?Download the message [here](https://artifacts.picoctf.net/c/154/message.txt).
### SOLUCIÓN

```
ZGSOCXPQUYHMILERVTBWNAFJDK

Qctcnrel Mcptzlo ztebc, fuwq z ptzac zlo bwzwcmd zut, zlo gtenpqw ic wqc gccwmc
xtei z pmzbb szbc ul fqusq uw fzb clsmebco. Uw fzb z gcznwuxnm bsztzgzcnb, zlo, >
wqzw wuic, nlhlefl we lzwntzmubwb—ex sentbc z ptczw rtukc ul z bsuclwuxus reulw
ex aucf. Wqctc fctc wfe tenlo gmzsh brewb lczt elc cjwtciuwd ex wqc gzsh, zlo z
melp elc lczt wqc ewqct. Wqc bszmcb fctc cjsccoulpmd qzto zlo pmebbd, fuwq zmm w>
zrrcztzlsc ex gntlubqco pemo. Wqc fcupqw ex wqc ulbcsw fzb actd tcizthzgmc, zlo,
wzhulp zmm wqulpb ulwe selbuoctzwuel, U senmo qztomd gmzic Ynruwct xet qub erulu>
tcbrcswulp uw.

Wqc xmzp ub: ruseSWX{5NG5717N710L_3A0MN710L_357GX9XX}

```

- El mensaje utiliza un cifrado de sustitución simple. La primera cadena de texto proporcionada (`ZGSOCXPQUYHMILERVTBWNAFJDK`) funciona como la clave de descifrado, mapeándose directamente en orden con el abecedario estándar (`ABCDEFGHIJKLMNOPQRSTUVWXYZ`).

- Al aplicar esta correspondencia inversa (Z=A, G=B, S=C, etc.) a la cadena cifrada final (`ruseSWX{5NG5717N710L_3A0MN710L_357GX9XX}`), manteniendo intactos los números y guiones bajos, se obtiene el texto en claro.

- Flag:  picoCTF{5UB5717U710N_3V0LU710N_357BF9FF}
### NOTAS ADICIONALES


### REFERENCIAS