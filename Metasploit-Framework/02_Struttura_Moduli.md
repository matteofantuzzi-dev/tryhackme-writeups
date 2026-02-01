# Architettura dei Moduli MSF

Percorso locale (AttackBox): `/opt/metasploit-framework/embedded/framework/modules`

| Nome Modulo | Funzione |
| :--- | :--- |
| **Exploits** | Contiene il codice per sfruttare le falle (diviso per OS). |
| **Auxiliary** | Scanner, fuzzer, crawler e strumenti di raccolta info. |
| **Payloads** | Istruzioni da eseguire (Singles, Stagers, Stages). |
| **Post** | Moduli per la fase di post-exploitation (es. rubare hash password). |
| **Encoders** | Codifica il payload per tentare di eludere gli Antivirus (basati su firma). |
| **Evasion** | Moduli specifici per bypassare difese attive (es. Windows Defender). |
| **NOPs** | Istruzioni "vuote" per mantenere fissa la dimensione del payload. |
