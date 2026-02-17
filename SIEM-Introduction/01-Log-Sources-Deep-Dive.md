# 📂 Log Sources & Data Generation

Nella difesa, la visibilità è tutto. I log si dividono in due grandi famiglie che devono essere ingerite dal SIEM.

### 💻 Host-Centric Logs (Endpoint)
Catturano ciò che accade all'interno del sistema operativo.
* **Windows (Event Viewer):** Ogni evento ha un ID unico.
  * **Event ID 104:** Fondamentale. Indica che qualcuno ha cancellato i log (tentativo di nascondere le tracce).
  * **Event ID 4688:** Creazione processo. Se vedi `whoami` o `mimikatz`, sei sotto attacco.
* **Linux (System Logs):**
  * `/var/log/auth.log`: Tentativi di login (Brute force detection).
  * `/var/log/httpd/`: Analisi di attacchi Web (SQLi, XSS).

### 🌐 Network-Centric Logs (Traffico)
Catturano il movimento tra i dispositivi.
* **Firewall/IDS/IPS:** Rilevano tentativi di connessione a porte chiuse o firme di malware note.
* **VPN Logs:** Monitorano accessi remoti (fondamentali per rilevare accessi da IP geograficamente impossibili).

### ⚙️ Metodi di Ingestione
Come arrivano i log al SIEM?
1. **Agents/Forwarders:** Software leggeri (es. Splunk Universal Forwarder) installati sull'host.
2. **Syslog:** Protocollo standard per inviare log in tempo reale via rete.
3. **Port Forwarding:** Il SIEM "ascolta" su una porta specifica e riceve i dati.
