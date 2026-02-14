# 🛡️ Difesa contro il Brute Force

Come difendere un'organizzazione dagli attacchi automatizzati eseguiti con tool come Hydra.

### 1. Policy sulle Password (Password Policy)
- Imporre una lunghezza minima (minimo 12-16 caratteri).
- Richiedere complessità (numeri, simboli, maiuscole).

### 2. Account Lockout e Throttling
- **Lockout**: Bloccare temporaneamente l'account dopo 5 tentativi errati.
- **Throttling**: Introdurre un ritardo crescente tra un tentativo e l'altro.

### 3. Autenticazione a due fattori (2FA / MFA)
L'implementazione del 2FA rende il Brute Force quasi del tutto inefficace, poiché la sola password non è sufficiente per accedere.

### 4. Monitoraggio e Logging
Utilizzare sistemi come **Fail2Ban** per analizzare i log dei tentativi di accesso e bannare automaticamente gli indirizzi IP che mostrano comportamenti tipici di Hydra (molte richieste in poco tempo).
