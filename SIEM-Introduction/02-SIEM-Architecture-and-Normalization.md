# ⚙️ SIEM: Normalization & Correlation

Un SIEM non è solo un database, è un motore di elaborazione.

### 🔄 Il Processo di Normalizzazione (Parsing)
I log arrivano in formati diversi (JSON, XML, Key-Value). Il SIEM esegue il **Parsing**:
* **Raw Log:** `May 28 13:04:20 user=molly status=fail`
* **Normalized Field:** `User: molly | Status: Failure | Timestamp: 2026-02-17`

**Perché è vitale?** Senza normalizzazione non potresti cercare "Tutti i login falliti dell'utente Molly" su macchine Windows e Linux contemporaneamente.

### 🔗 Log Correlation
La correlazione unisce eventi apparentemente isolati.
* **Esempio di scenario:**
  1. Login fallito (Firewall).
  2. Login riuscito da IP insolito (VPN).
  3. Esecuzione script `base64` (Windows Event ID 4688).
* **Risultato:** Il SIEM genera un alert unico per **"Compromissione Account e possibile Beaconing"**.
