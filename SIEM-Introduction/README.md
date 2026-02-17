# 🛡️ Security Information and Event Management (SIEM) Introduction

Benvenuti in questa sezione del mio repository dedicata alla **Difesa Cibernetica** e alle operazioni di un **SOC (Security Operations Center)**. 

In questo modulo ho approfondito il funzionamento del **SIEM**, la soluzione software centrale che ogni analista di sicurezza utilizza per raccogliere, normalizzare e correlare i log provenienti da tutta l'infrastruttura aziendale.

## 🎯 Obiettivi Formativi
* Comprendere la differenza tra log **Host-Centric** e **Network-Centric**.
* Identificare i limiti dell'analisi di log isolati e l'importanza della centralizzazione.
* Analizzare le fasi di **Parsing**, **Normalizzazione** e **Correlazione**.
* Apprendere il processo di **Alert Triage** e investigazione degli incidenti.

---

## 📁 Struttura della Documentazione

Per facilitare la consultazione, ho suddiviso gli appunti tecnici in tre guide specialistiche:

1.  **[01-Log-Sources-Deep-Dive.md](./01-Log-Sources-Deep-Dive.md)** *Analisi dettagliata delle sorgenti dati: Windows Event IDs, percorsi log Linux e log di rete.*

2.  **[02-SIEM-Architecture-and-Normalization.md](./02-SIEM-Architecture-and-Normalization.md)** *Come il SIEM trasforma i dati grezzi in informazioni utili tramite la normalizzazione e la creazione di regole di correlazione.*

3.  **[03-Alert-Triage-Workflow.md](./03-Alert-Triage-Workflow.md)** *Il lavoro pratico dell'analista: distinguere tra True e False Positive e gestire il ciclo di vita di un alert.*

---

## 💡 Key Takeaway: Dal Red Team al Blue Team
Dopo aver testato attacchi di brute force con **Hydra**, in questa room ho imparato come quegli stessi attacchi appaiono "dall'altra parte della barricata". 

Un attacco che genera migliaia di tentativi di login falliti viene rilevato dal SIEM grazie a regole specifiche:
> `IF LogSource=WinEventLog AND EventID=4625 (Failed Login) COUNT > 5 IN 10s -> TRIGGER ALERT`

Questo modulo mi ha permesso di capire che la sicurezza non è fatta solo di attacco, ma di **visibilità** e **capacità di risposta rapida**.

---

## 🛠️ Strumenti e Tecnologie
* **SIEM:** Splunk, ELK Stack.
* **Log Analysis:** Windows Event Viewer, Linux `/var/log/`.
* **Metodologia:** Triage di Livello 1 (Tier 1 Analyst).

---
*Note: Questa documentazione è stata prodotta durante il percorso formativo su TryHackMe - SOC Fundamentals Path.*
