**Contenuto:**
```markdown
# 🐚 Fase 3: Gestione Professionale delle Sessioni

Ottenere l'accesso è solo l'inizio. Gestire correttamente le sessioni è ciò che distingue un principiante da un professionista.

## 1. Comandi di Controllo Sessione
Quando un exploit ha successo, viene aperta una sessione.
-  check: comando per verificare la vulnerabilità senza lanciare l'exploit
-  exploit: lancia l'attacco
-  run -j: lancia l'attacco come Job in background (permette di continuare a usare la console mentre l'exploit lavora)
- `CTRL + Z` o `background`: Sospende la sessione attuale e torna al prompt `msf6`.
- `sessions -l`: Elenca tutte le sessioni attive con ID, tipo e utente.
- `sessions -i [ID]`: Rientra in una sessione specifica.
- `sessions -k [ID]`: Chiude (uccide) una sessione non più necessaria.
- `sessions -u [ID]`: Esegue l'upgrade automatico da shell standard a **Meterpreter**.



## 2. Risoluzione dei Problemi (Troubleshooting)
Se l'attacco fallisce, analizza questi scenari:
- **Exploit completed, but no session created**:
  - Il firewall del target blocca la connessione in uscita.
  - L'IP in `LHOST` è sbagliato (controlla la VPN).
  - Il payload non è compatibile con l'architettura (x86 vs x64).
- **Session died unexpectedly**:
  - Il servizio target è crashato.
  - Un Antivirus/EDR ha rilevato e ucciso il processo del payload.

## 3. Best Practices e Manutenzione
- **Persistenza dell'IP**: Se la VPN cade, il tuo IP `tun0` cambia. Devi aggiornare `LHOST` in tutti i moduli.
- **Rank dei Moduli**: Prediligi sempre exploit con Rank **Excellent** per garantire la stabilità del sistema vittima.
- **Gestione Job**: Usa `jobs -l` per monitorare gli exploit che girano in background e `jobs -k [ID]` per fermarli.
