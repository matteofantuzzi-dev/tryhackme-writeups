# 🌊 Layer 2 Attack: MAC Flooding

Il MAC Flooding è un attacco indirizzato agli **Switch** di rete. L'obiettivo è compromettere la sicurezza della tabella CAM (Content Addressable Memory).

## 🧠 Concetti Teorici
Uno switch mantiene una **CAM Table** (o MAC Table) per mappare quale indirizzo MAC si trova su quale porta fisica. 
- Quando la tabella è piena, lo switch non sa più dove mandare i pacchetti.
- **Fail-Open Mode**: In stato di saturazione, molti switch iniziano a comportarsi come un vecchio "Hub", trasmettendo il traffico di una porta a **tutte** le altre porte (Broadcasting).



## 🛠️ Tool e Comandi: macof
`macof` è uno strumento della suite dsniff che genera migliaia di indirizzi MAC casuali al secondo.

### Comando utilizzato:
```bash
# Esecuzione del MAC Flooding sull'interfaccia specificata
macof -i eth0 -n 100
-i eth0 -> specifica la rete
-n 100 -> Numero di pacchetti da inviare (nelle room THM si usa spesso un numero alto o infinito).
