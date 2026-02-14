# 🛠️ Guida Pratica ai Comandi Hydra

La sintassi di Hydra varia a seconda del protocollo, ma segue una logica costante.

## 🗝️ Flag Universali
- `-l [username]`: Usa un singolo nome utente specifico.
- `-L [file.txt]`: Usa una lista di nomi utente (wordlist).
- `-p [password]`: Usa una singola password specifica.
- `-P [file.txt]`: Usa una wordlist di password.
- `-t [n]`: Numero di thread (connessioni parallele). Più è alto, più è veloce, ma può bloccare il servizio.
- `-V`: Modalità Verbose (mostra ogni tentativo).
- `-s [port]`: Specifica una porta non standard.

---

## 🖥️ Caso 1: Attacco SSH
SSH è un bersaglio comune per ottenere l'accesso remoto.
```bash
hydra -l root -P /usr/share/wordlists/rockyou.txt [IP_TARGET] -t 4 ssh
