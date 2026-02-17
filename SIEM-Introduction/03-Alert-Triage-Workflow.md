# 🚨 Alert Investigation & Triage Workflow

Cosa fa un analista quando "suona la sirena" sul SIEM?

### ⚖️ Fase 1: Classificazione (Triage)
L'analista deve determinare la natura dell'alert:
* **True Positive (TP):** L'attività sospetta è reale e maligna.
* **False Positive (FP):** Un'attività lecita ha fatto scattare la regola (es. un admin che testa uno script).
* **True Negative:** Il sistema non segnala nulla e non c'è attività maligna.
* **False Negative:** Il "Sogno proibito" dell'hacker: l'attacco avviene ma il SIEM non lo vede.

### 🛠️ Fase 2: Action Plan post-investigazione
Se l'alert è un **True Positive**, si procede con:
1. **Isolamento:** Staccare l'host dalla rete per fermare il malware.
2. **Blocking:** Bloccare l'IP dell'attaccante sul Firewall.
3. **Tuning:** Se era un False Positive, si modifica la regola per renderla più precisa e ridurre il "rumore".

### 📊 Dashboard Monitoring
Gli analisti monitorano grafici in tempo reale per individuare anomalie visive:
* Picchi improvvisi di traffico in uscita (Exfiltration).
* Aumento dei volumi di "Failed Logins" (Brute Force).
* Top 10 domini più visitati (Possibile C2 - Command & Control).
