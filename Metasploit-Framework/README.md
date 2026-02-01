# 🛡️ Metasploit Framework: Note e Cheat Sheet

Benvenuti nel mio repository dedicato all'apprendimento di **Metasploit Framework**. Queste note sono state raccolte durante il completamento della stanza dedicata su **TryHackMe** e servono come guida rapida per penetration testing e sicurezza informatica.

---

## 📂 Struttura della Documentazione

Il materiale è diviso in tre sezioni principali per facilitare la consultazione:

1.  **[Concetti Base](./01_Concetti_Base.md)**: Definizioni di Exploit, Vulnerability, Payload e la differenza cruciale tra payload *Single* e *Staged*.
2.  **[Architettura dei Moduli](./02_Struttura_Moduli.md)**: Una panoramica di come è organizzato il framework (Auxiliary, Exploits, Post, Evasion, ecc.).
3.  **[Cheat Sheet Comandi](./03_Comandi_Rapidi.md)**: Una lista dei comandi essenziali da usare dentro `msfconsole` per muoversi velocemente tra i moduli.

---

## 🚀 Quick Start (Workflow Tipico)

Per chi ha fretta, ecco la sequenza standard di comandi per un attacco:

```bash
# 1. Avvio e ricerca
msfconsole
search [vulnerabilità]

# 2. Selezione e configurazione
use [modulo]
show options
set RHOSTS [Target_IP]
set LHOST [Your_IP]

# 3. Lancio
exploit


---

## ⚠️ Disclaimer (Scopo Educativo)

Tutto il contenuto di questo repository è destinato esclusivamente a **scopi educativi e di ricerca sulla sicurezza informatica**. 

- L'autore non si assume alcuna responsabilità per l'uso improprio di queste informazioni.
- Non utilizzare mai questi strumenti o tecniche su reti, sistemi o dispositivi senza l'autorizzazione esplicita dei proprietari.
- L'accesso non autorizzato a sistemi informatici è un reato perseguibile legalmente.

**Ricorda: L'obiettivo è imparare a difendere i sistemi capendo come vengono attaccati.**
