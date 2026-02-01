# Tipologie di Scansione Nmap

Nmap utilizza diversi modi per interagire con le porte TCP/UDP. Ecco i principali:

## 1. TCP Connect Scan (`-sT`)
- **Come funziona:** Completa il "Three-way Handshake" di TCP (SYN, SYN/ACK, ACK).
- **Quando usarlo:** Quando l'utente non ha privilegi di root (Sudo).
- **Svantaggio:** È facilmente rilevabile dai log del sistema target.

## 2. SYN Scan (`-sS`)
- **Come funziona:** Invia un pacchetto SYN e aspetta un SYN/ACK, ma invia un RST (Reset) invece dell'ACK finale. Non completa mai la connessione.
- **Vantaggio:** Più veloce e "nascosto" (Stealth), non appare spesso nei log delle applicazioni.
- **Requisito:** Richiede privilegi di root.

## 3. UDP Scan (`-sU`)
- **Come funziona:** Invia pacchetti UDP ai target. Essendo UDP un protocollo senza connessione, è molto più lento.
- **Problema:** Spesso le porte non rispondono se sono aperte, rendendo difficile la diagnosi.
