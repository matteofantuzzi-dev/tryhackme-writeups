# 🏛️ Architettura del Metasploit Framework (MSF)

Metasploit non è un singolo strumento, ma un ecosistema modulare. La sua potenza risiede nella separazione tra il codice che "apre la porta" (Exploit) e il codice che "entra" (Payload).

## 1. Anatomia dei Moduli
Ogni modulo ha un ruolo specifico nel processo di Penetration Testing:

* **Exploits**: Codice che sfrutta una specifica vulnerabilità (buffer overflow, misconfiguration, etc.) per forzare l'esecuzione di codice arbitrario.
* **Auxiliary**: Moduli che eseguono compiti senza payload. Includono:
    * *Scanner*: Per mappare servizi (es. `scanner/ssh/ssh_login`).
    * *Fuzzer*: Per inviare dati casuali e trovare nuovi bug.
    * *Dos*: Per testare la resistenza ai Denial of Service.
* **Payloads**: Il "corpo" dell'attacco. Si dividono in tre sottotipi:
    * **Singles (Inline)**: Autocontenuti (es. `windows/shell_reverse_tcp`). Più semplici ma più grandi in dimensioni.
    * **Stagers**: Piccoli frammenti di codice che stabiliscono una connessione iniziale per scaricare il resto del payload.
    * **Stages**: Il payload finale (es. Meterpreter) scaricato dallo Stager.
* **Post**: Moduli per la fase successiva alla compromissione (raccolta credenziali, enumerazione locale).



## 2. Reverse Shell vs Bind Shell
* **Reverse Shell (Consigliata)**: Il target si connette verso la tua macchina (AttackBox). Utile per bypassare i firewall che bloccano le connessioni in entrata ma permettono quelle in uscita.
* **Bind Shell**: La tua macchina si connette al target su una porta aperta dall'exploit. Spesso bloccata dai firewall.
