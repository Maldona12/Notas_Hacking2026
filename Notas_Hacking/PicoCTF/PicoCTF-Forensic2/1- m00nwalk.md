### [m00nwalk](https://play.picoctf.org/practice/challenge/26)

### DESCRIPCIÓN

Decode this [message](https://challenge-files.picoctf.net/c_fickle_tempest/c9834b19f74a20802d7c53dc42fe1ccd8a69da4cf5c38fa5b6aab8ec472efdd3/message.wav) from the moon.
### SOLUCIÓN

- Dado que la instalación vía `pip` y el software `QSSTV` fallaron en la VM, se descargó el decodificador directamente desde su repositorio de GitHub.
    
- Comandos utilizados:
    
    - `git clone https://github.com/colaclanth/sstv.git`
    
    - `sudo apt install python3-pil python3-numpy python3-scipy`
      
    - `python3 -m sstv -d message.wav -o resultado.png`

- La imagen `resultado.png` contiene la bandera tras procesar el audio en modo **Scottie 1**

picoCTF{beep_boop_im_in_space}
### NOTAS ADICIONALES


### REFERENCIAS