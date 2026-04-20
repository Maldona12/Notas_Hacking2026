### DESCRIPCIÓN

Class, take your seats! It's PRIME-time for a quiz...

nc fickle-tempest.picoctf.net 57390
### SOLUCIÓN


```
from pwn import *

HOST = "fickle-tempest.picoctf.net"
PORT = 57390 # ACTUALIZAR EL PUERTO
r = remote(HOST, PORT) 

# Diccionario para recordar p y q si el servidor reusa un 'n'
n_factors = {}

print("[*] Iniciando resolución dinámica del Quiz...")

while True:
    try:
        line = r.recvline().decode()
        
        if "picoCTF{" in line:
            print(f"\n[🏆] ¡FLAG ENCONTRADA!\n{line.strip()}")
            break
            
        if "#### NEW PROBLEM ####" in line:
            data = {}
            while True:
                l = r.recvline().decode().strip()
                if "##### PRODUCE THE FOLLOWING ####" in l:
                    break
                if ":" in l:
                    key, val = l.split(":")
                    data[key.strip()] = int(val.strip())
            
            target = r.recvline().decode().strip()
            print(f"\n[*] Objetivo a calcular: {target}")
            print(f"[*] Variables recibidas: {list(data.keys())}")

            # Guardar p y q por si el servidor recicla el módulo n
            if "p" in data and "q" in data:
                n_val = data.get("n", data["p"] * data["q"])
                n_factors[n_val] = (data["p"], data["q"])

            ans = None
            possible = True

            # --- LÓGICA DINÁMICA ---
            if target == "n":
                if "p" in data and "q" in data:
                    ans = data["p"] * data["q"]
                else: possible = False
                    
            elif target == "q" or target == "p":
                factor = "p" if target == "q" else "q"
                if factor in data and "n" in data:
                    ans = data["n"] // data[factor]
                else: possible = False

            elif "totient" in target:
                if "p" in data and "q" in data:
                    ans = (data["p"] - 1) * (data["q"] - 1)
                else: possible = False

            elif target == "d":
                e = data.get("e")
                t = data.get("totient(n)", data.get("totient"))
                
                if not t and "p" in data and "q" in data:
                    t = (data["p"] - 1) * (data["q"] - 1)
                
                if e and t:
                    ans = pow(e, -1, t)
                else: possible = False

            elif target == "ciphertext":
                m = data.get("plaintext", data.get("m"))
                if m is not None and "e" in data and "n" in data:
                    ans = pow(m, data["e"], data["n"])
                else: possible = False

            elif target == "plaintext":
                c = data.get("ciphertext", data.get("c"))
                if c is not None and "e" in data:
                    n_val = data.get("n")
                    p = data.get("p")
                    q = data.get("q")
                    
                    # --- LÓGICA DE AUTOCOMPLETADO ---
                    if n_val:
                        if p and not q:
                            q = n_val // p
                        elif q and not p:
                            p = n_val // q
                    
                    if not p or not q:
                        if n_val in n_factors:
                            p, q = n_factors[n_val]
                            
                    if p and q:
                        phi = (p - 1) * (q - 1)
                        d = pow(data["e"], -1, phi)
                        if not n_val:
                            n_val = p * q
                        ans = pow(c, d, n_val)
                    else:
                        possible = False 
                else: possible = False
            else:
                possible = False

            # --- ENVIAR RESPUESTA ---
            r.recvuntil(b"IS THIS POSSIBLE and FEASIBLE? (Y/N):")
            
            if possible and ans is not None:
                print(f"[+] Es factible. Enviando respuesta calculada...")
                r.sendline(b"Y")
                r.recvuntil(b":")
                r.sendline(str(ans).encode())
                
                # Intentar decodificar a texto si es el plaintext final
                if target == "plaintext":
                    try:
                        hex_str = hex(ans)[2:]
                        if len(hex_str) % 2 != 0:
                            hex_str = '0' + hex_str
                        texto = bytes.fromhex(hex_str).decode()
                        print(f"\n[!] ---> TEXTO DECODIFICADO: {texto} <---")
                    except:
                        pass
            else:
                print("[-] No es factible. Enviando 'N'.")
                r.sendline(b"N")

    except EOFError:
        print("\n[*] Conexión cerrada por el servidor.")
        break
    except Exception as e:
        print(f"\n[!] Error crítico: {e}")
        break
```
### NOTAS ADICIONALES


### REFERENCIAS