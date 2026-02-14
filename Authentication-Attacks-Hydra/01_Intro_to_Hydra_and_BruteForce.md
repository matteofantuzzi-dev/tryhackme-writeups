# ⚡ THC-Hydra: Online Password Cracking

Hydra è uno dei tool più veloci e flessibili per eseguire attacchi di **Brute Force** e **Dictionary Attack** contro servizi che richiedono autenticazione. A differenza del cracking offline (come John the Ripper), Hydra interagisce direttamente con il servizio attivo (Online).

## 🧠 Cos'è un attacco Brute Force?
Consiste nel tentare sistematicamente tutte le combinazioni possibili di credenziali finché non si trova quella corretta. 
- **Dictionary Attack**: Utilizza una lista predefinita di password comuni (es. `rockyou.txt`).
- **Default Credentials**: Spesso i sistemi (CCTV, Router) nascono con `admin:admin` o `admin:password`. Hydra permette di testare queste falle in pochi secondi.

## 🌐 Protocolli Supportati
Hydra è estremamente versatile e supporta oltre 50 protocolli, tra cui:
- **Remote Access**: SSH, RDP, VNC, Telnet.
- **Web**: HTTP-GET, HTTP-POST-FORM (Login pages), HTTPS.
- **Databases**: MySQL, PostgreSQL, MongoDB.
- **File Transfer**: FTP, SMB.
- **Mail**: POP3, IMAP, SMTP.



---

## 🛡️ Best Practices per la Sicurezza
L'esistenza di tool come Hydra sottolinea l'importanza di:
1. **Password Forti**: Almeno 12-16 caratteri con simboli e numeri.
2. **Account Lockout**: Bloccare l'account dopo 3-5 tentativi falliti.
3. **2FA (Two-Factor Authentication)**: Rendere inutile la sola password.
