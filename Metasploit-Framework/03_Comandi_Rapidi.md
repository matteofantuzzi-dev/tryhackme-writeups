# Cheat Sheet Metasploit

## Gestione Console
- `msfconsole`: Avvia il framework.
- `search [nome]`: Cerca un modulo (es. `search eternalblue`).
- `use [n. o percorso]`: Carica un modulo.
- `info`: Mostra dettagli, autore e opzioni del modulo.
- `back`: Esci dal modulo corrente.

## Configurazione ed Esecuzione
- `show options`: Mostra i parametri necessari.
- `set RHOSTS [IP]`: Imposta l'indirizzo della vittima.
- `set LHOST [IP]`: Imposta l'indirizzo della tua macchina (per reverse shell).
- `exploit` o `run`: Lancia il modulo.
- `check`: Verifica se il target è vulnerabile senza lanciare l'exploit.

## Gestione Sessioni
- `CTRL + Z`: Mette la sessione attuale in background.
- `sessions -l`: Elenca tutte le sessioni attive.
- `sessions -i [ID]`: Riapre una sessione specifica.
