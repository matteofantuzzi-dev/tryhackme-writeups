# 🏗️ Architettura delle Applicazioni Web

Una web app moderna è composta da diversi strati. Identificare ogni componente permette di scegliere il giusto payload.

## 1. Front-End (Il lato Client)
- **HTML**: La struttura.
- **CSS**: Lo stile.
- **JavaScript**: La logica eseguita nel browser. *Attacco tipico: Cross-Site Scripting (XSS).*

## 2. Back-End (Il lato Server)
- **Server Web**: Apache, Nginx, IIS. Gestiscono le richieste HTTP.
- **Linguaggi Server-side**: PHP, Python (Django/Flask), Node.js, Java. Gestiscono la logica di business.
- **Database**: MySQL, PostgreSQL, MongoDB. Dove risiedono i dati. *Attacco tipico: SQL Injection.*



## 3. Cookies e Sessioni
Poiché l'HTTP è stateless, i server usano i **Cookie** per ricordarsi chi siamo.
- **Session Cookie**: Identificativo temporaneo salvato nel browser.
- **Set-Cookie Header**: Il modo in cui il server invia il cookie al client.
- **Rischi**: Se un attaccante ruba il tuo `SessionID`, può effettuare un **Session Hijacking** e spacciarsi per te senza password.
