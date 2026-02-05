# 🔍 Fase 1: Reconnaissance & Enumeration con Nmap

La ricognizione è la fase più importante: se non conosci il bersaglio, non puoi attaccarlo.

## Strategia di Scansione
Per identificare i vettori d'attacco su una macchina sconosciuta:
```bash
nmap -sS -sV -Pn -p 1-1000 [IP_TARGET]
 
Analisi dei Flag:
-sS (TCP SYN Scan): Conosciuto come "Half-Open scan". Non completa l'handshake TCP, rendendolo più veloce e difficile da loggare per i vecchi sistemi.

-sV (Version Detection): Interroga le porte aperte per determinare la versione esatta del servizio (es. Apache 2.4.41). Cruciale per cercare l'exploit corretto.

-Pn: Assume che l'host sia "vivo". Impedisce a Nmap di rinunciare se il target blocca i pacchetti ICMP (Ping).

-p 1-1000: Scansiona solo le porte "well-known". In Metasploit, porte comuni come 445 (SMB) o 80 (HTTP) sono spesso i primi bersagli.

