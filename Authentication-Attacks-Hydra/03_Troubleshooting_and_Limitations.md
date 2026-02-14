Qui inseriamo l'analisi dei problemi comuni per dimostrare capacità di problem-solving.

**Contenuto:**
```markdown
# 🔧 Hydra: Risoluzione dei Problemi e Limitazioni Tecniche

Eseguire un attacco di forza bruta online presenta diverse sfide tecniche che possono invalidare i risultati.

## 1. Connessioni Rifiutate e Threading
Se il numero di thread (`-t`) è troppo elevato:
- **Sintomo**: Il server smette di rispondere o restituisce errori di connessione.
- **Soluzione**: Abbassare il valore di `-t` (es. `-t 4` o `-t 1`). Alcuni server limitano il numero di connessioni simultanee per IP.

## 2. Falsi Positivi
Un errore comune è quando Hydra dichiara di aver trovato la password, ma questa non funziona.
- **Causa**: La stringa di fallimento (`F=`) è errata o troppo generica.
- **Verifica**: Controlla manualmente cosa risponde il server a un login errato (es. "Invalid credentials", "Access denied", "Login failed"). Assicurati di copiare la stringa esatta.

## 3. Rate Limiting e WAF
I Web Application Firewall (WAF) moderni bloccano l'IP dopo un certo numero di tentativi falliti.
- **Sintomo**: Hydra riceve codici di errore `403 Forbidden` o `429 Too Many Requests`.
- **Evasione**: È necessario utilizzare dei proxy o rallentare drasticamente l'attacco, rendendo però il Brute Force spesso impraticabile.



## 4. Default Credentials (Il primo passo)
Prima di avviare un attacco lungo ore, testa sempre le credenziali di default. Molti dispositivi (CCTV, router, CMS) vengono installati con:
- `admin : admin`
- `admin : password`
- `root : root`
