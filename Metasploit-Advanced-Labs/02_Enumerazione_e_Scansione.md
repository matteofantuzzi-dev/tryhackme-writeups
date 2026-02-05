# 🔍 Fase 1: Reconnaissance & Enumeration con Nmap

La ricognizione è la fase più importante: se non conosci il bersaglio, non puoi attaccarlo.

## Strategia di Scansione
Per identificare i vettori d'attacco su una macchina sconosciuta:
```bash
nmap -sS -sV -Pn -p 1-1000 [IP_TARGET]
