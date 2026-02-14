# 🌐 Attacchi ai Web Form con Hydra (HTTP-POST)

L'attacco ai moduli di login web è complesso perché Hydra deve simulare esattamente ciò che fa un browser quando premi "Login".

## 1. Anatomia del comando HTTP-POST-FORM
La sintassi segue questo schema rigido:
`"<path>:<request_body>:<condition>"`

### Esempio Pratico:
```bash
hydra -l admin -P passlist.txt [IP_TARGET] http-post-form "/login.php:user=^USER^&pass=^PASS^:F=incorrect" -V

Analisi dei Componenti:
/login.php (Path): La pagina che riceve i dati. Spesso non è la pagina dove inserisci i dati, ma quella indicata nell'attributo action del tag <form>.

user=^USER^&pass=^PASS^ (Body):

user e pass sono i nomi dei campi (attributo name) nel codice HTML.

^USER^ e ^PASS^ sono i segnaposto che Hydra sostituirà con le parole delle tue wordlist.

F=incorrect (Condition):

F sta per False (condizione di fallimento).

Hydra considera il tentativo fallito se nella risposta del server appare la parola "incorrect".

Nota: Puoi usare anche S=success per indicare la condizione di successo, ma F è solitamente più affidabile.
