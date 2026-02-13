# 🌐 Il Protocollo HTTP/HTTPS

L'HTTP (HyperText Transfer Protocol) è un protocollo "stateless" (senza stato) basato su un modello Client-Server. Comprendere i messaggi HTTP è la base per qualsiasi attacco Web (SQLi, XSS, IDOR).

## 1. Anatomia di una Richiesta (Request)
Ogni richiesta inviata dal browser al server contiene:
- **Verbo HTTP (Metodo)**: Definisce l'azione (GET, POST, PUT, DELETE).
- **Headers**: Metadati come `User-Agent`, `Cookie`, `Host`.
- **Body**: Dati inviati al server (usato principalmente nei metodi POST e PUT).



[Image of HTTP request and response message structure]


## 2. Metodi HTTP Comuni
| Metodo | Funzione | Rischio di Sicurezza |
| :--- | :--- | :--- |
| **GET** | Recupera dati. | I dati sensibili passano nell'URL (visibili nei log). |
| **POST** | Invia dati al server. | Spesso bersaglio di SQL Injection o Cross-Site Request Forgery. |
| **PUT** | Carica o aggiorna file. | Se mal configurato, permette l'upload di Shell (RCE). |
| **DELETE** | Rimuove risorse. | Può essere abusato se mancano controlli di autorizzazione. |

## 3. Codici di Stato (Status Codes)
- **200 OK**: Richiesta riuscita.
- **301/302 Redirect**: La risorsa è altrove.
- **403 Forbidden**: Permesso negato (WAF o permessi file).
- **404 Not Found**: Risorsa inesistente (utile per il directory brute-forcing).
- **500 Internal Server Error**: Errore del server (spesso indica che un nostro input ha rotto il codice, possibile bug).
