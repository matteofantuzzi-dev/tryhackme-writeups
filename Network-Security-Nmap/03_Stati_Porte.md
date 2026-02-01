# Come leggere i risultati di Nmap

Dopo una scansione, Nmap assegna uno stato ad ogni porta:

1. **Open (Aperta)**: Un'applicazione è in ascolto e accetta connessioni. È il nostro obiettivo principale.
2. **Closed (Chiusa)**: La porta risponde con un pacchetto RST, indicando che non c'è alcun servizio attivo, ma l'host è raggiungibile.
3. **Filtered (Filtrata)**: Nmap non riceve risposta. Indica solitamente che un **Firewall** sta bloccando il pacchetto o la risposta.
4. **Unfiltered**: La porta è accessibile ma non si sa se sia aperta o chiusa (raro, si vede in ACK scan).
