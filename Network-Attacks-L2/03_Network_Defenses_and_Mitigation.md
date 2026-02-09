# 🛡️ Network Defenses: Hardening del Layer 2

Dopo aver compreso come sferrare attacchi come il MAC Flooding e l'ARP Spoofing, è fondamentale implementare strategie di difesa. La sicurezza a livello 2 (Data Link) è la prima linea di difesa in una rete aziendale.

## 1. Difesa contro il MAC Flooding: Port Security

La saturazione della tabella CAM può essere prevenuta istruendo lo switch a "diffidare" dal traffico anomalo.

### Configurazione Cisco Port Security
- **Static Port Security**: Si definisce manualmente quale indirizzo MAC può collegarsi a una porta.
- **Sticky MAC**: Lo switch apprende il primo MAC che si connette e lo scrive nella configurazione (`running-config`). Se un altro MAC tenta l'accesso, la porta viene disattivata.
- **Violation Modes**:
    - `Protect`: Scarta i pacchetti del MAC sconosciuto.
    - `Restrict`: Scarta i pacchetti e genera un log di notifica (SNMP).
    - `Shutdown`: Disabilita immediatamente la porta fisica (richiede intervento manuale).



---

## 2. Difesa contro l'ARP Spoofing: DAI e DHCP Snooping

L'ARP Spoofing si basa sulla natura "senza stato" dell'ARP. Per bloccarlo servono meccanismi che verifichino l'identità dei mittenti.

### A. DHCP Snooping
Prima di attivare difese avanzate, lo switch deve creare un database di fiducia. Il **DHCP Snooping** monitora i messaggi DHCP e crea una tabella di associazione IP-MAC-Porta legittima. Tutte le porte non collegate al server DHCP sono considerate "untrusted".

### B. Dynamic ARP Inspection (DAI)
Il DAI utilizza il database creato dal DHCP Snooping. Quando arriva un pacchetto ARP, lo switch controlla se la coppia IP-MAC corrisponde a quella registrata.
- Se la coppia è **falsa** (come nell'ARP Spoofing), lo switch scarta il pacchetto.



---

## 3. Strategie di Segmentazione e Crittografia

Se le difese di rete falliscono, i dati devono comunque rimanere protetti.

- **VLAN (Virtual LAN)**: Dividere la rete in sottoreti logiche limita il raggio d'azione dell'attaccante. Un attacco L2 in una VLAN non influisce sulle altre.
- **Isolamento delle porte (Private VLAN)**: Impedisce ai dispositivi nella stessa VLAN di comunicare tra loro, obbligandoli a passare per un firewall/router (Layer 3).
- **Adozione di Protocolli Criptati**: L'uso sistematico di **HTTPS, SSH, SFTP e VPN** rende inutile lo sniffing del traffico. Anche se l'attaccante si posiziona come Man-in-the-Middle, vedrà solo traffico cifrato indecifrabile.
