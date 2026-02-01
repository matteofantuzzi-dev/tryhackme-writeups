# Cheat Sheet Comandi Nmap

## Selezione delle Porte
- `-p 80` : Scansiona una porta specifica.
- `-p 1-1000` : Scansiona un range di porte (es. tutte quelle sotto la 1000).
- `-p-` : Scansiona tutte le 65535 porte.
- `-F` : Fast scan (scansiona solo le 100 porte più comuni).

## Rilevamento e Aggressività
- `-sV` : **Service Version Detection**. Tenta di determinare la versione del servizio (es. Apache 2.4.41).
- `-O` : **OS Detection**. Tenta di capire il sistema operativo (Linux, Windows, ecc.).
- `-A` : **Aggressive Mode**. Attiva insieme: OS detection, versioning, script scan e traceroute.
- `-Pn` : **No Ping**. Salta la verifica se l'host è vivo. Utile se il target ha un firewall che blocca i ping.

## Formati di Output
- `-oN [nome_file]` : Salva il risultato in un file di testo normale.
- `-oG [nome_file]` : Salva in formato "Grepable" (facile da filtrare con il comando `grep`).
