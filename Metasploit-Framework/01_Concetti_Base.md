# Fondamenti di Metasploit

## Definizioni Principali
- **Vulnerability**: Un difetto nel design o nella logica del sistema (il "buco").
- **Exploit**: Il codice che sfrutta la vulnerabilità per ottenere l'accesso.
- **Payload**: Il codice che viene eseguito sul target dopo l'exploit (cosa vogliamo ottenere).

## Tipi di Payload
Metasploit distingue i payload tramite la punteggiatura nel nome:

1. **Singles (Inline)**: Codice auto-contenuto.
   - *Sintassi:* `_` (es. `shell_reverse_tcp`).
   - *Vantaggio:* Più stabile e non richiede download extra.
2. **Staged**: Diviso in due fasi (Stager + Stage).
   - *Sintassi:* `/` (es. `shell/reverse_tcp`).
   - *Vantaggio:* Lo stager iniziale è molto piccolo, ideale per exploit con spazio limitato.

## Autori famosi
- Modulo `ssh_login`: Fornito da **todb** (Tod Beardsley).
